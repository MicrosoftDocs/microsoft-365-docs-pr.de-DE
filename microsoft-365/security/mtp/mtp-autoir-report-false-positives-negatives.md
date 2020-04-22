---
title: Behandeln falsch positiver oder falscher negativer Daten in der Luft in Microsoft Threat Protection
description: Wurde in Microsoft Threat Protection etwas übersehen oder fälschlicherweise von Air erkannt? Hier erfahren Sie, wie Sie falsch positive Ergebnisse oder falsch negative Informationen zur Analyse an Microsoft übermitteln.
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
ms.date: 01/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 4030469b54d9a3a9c6f2eaceae384d39ea7f3e20
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637080"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="7a033-105">Behandeln von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="7a033-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="7a033-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7a033-106">**Applies to:**</span></span>
- <span data-ttu-id="7a033-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a033-107">Microsoft Threat Protection</span></span>

<span data-ttu-id="7a033-108">Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) im Microsoft Threat Protection-Vorgang fehl am oder falsch erkannt?</span><span class="sxs-lookup"><span data-stu-id="7a033-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="7a033-109">Es gibt Schritte, die Sie ausführen können, um es zu beheben.</span><span class="sxs-lookup"><span data-stu-id="7a033-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="7a033-110">Sie können:</span><span class="sxs-lookup"><span data-stu-id="7a033-110">You can:</span></span>

- <span data-ttu-id="7a033-111">[Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="7a033-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>

- <span data-ttu-id="7a033-112">[Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="7a033-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 

- <span data-ttu-id="7a033-113">[Rückgängigmachen von auf Geräten ausgeführten Korrekturaktionen](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="7a033-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="7a033-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="7a033-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="7a033-115">Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="7a033-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="7a033-116">Element verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="7a033-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="7a033-117">Dienst</span><span class="sxs-lookup"><span data-stu-id="7a033-117">Service</span></span>  |<span data-ttu-id="7a033-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7a033-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7a033-119">-E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="7a033-119">- Email message</span></span> <br/><span data-ttu-id="7a033-120">-E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="7a033-120">- Email attachment</span></span> <br/><span data-ttu-id="7a033-121">-URL in einer e-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="7a033-121">- URL in an email message</span></span><br/><span data-ttu-id="7a033-122">-URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="7a033-122">- URL in an Office file</span></span>      |[<span data-ttu-id="7a033-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a033-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="7a033-124">Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="7a033-124">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="7a033-125">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="7a033-125">File or app on a device</span></span>    |[<span data-ttu-id="7a033-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a033-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="7a033-127">Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="7a033-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="7a033-128">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="7a033-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="7a033-129">Szenario</span><span class="sxs-lookup"><span data-stu-id="7a033-129">Scenario</span></span> |<span data-ttu-id="7a033-130">Dienst</span><span class="sxs-lookup"><span data-stu-id="7a033-130">Service</span></span> |<span data-ttu-id="7a033-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7a033-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="7a033-132">-Eine Warnung wird durch eine legitime Verwendung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="7a033-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="7a033-133">-Eine Warnung ist falsch</span><span class="sxs-lookup"><span data-stu-id="7a033-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="7a033-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7a033-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="7a033-135">oder</span><span class="sxs-lookup"><span data-stu-id="7a033-135">or</span></span> <br/>[<span data-ttu-id="7a033-136">Erkennung erweiterter Azure-Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="7a033-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="7a033-137">Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal</span><span class="sxs-lookup"><span data-stu-id="7a033-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="7a033-138">Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, auch wenn Sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="7a033-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="7a033-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a033-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="7a033-140">Erstellen eines benutzerdefinierten Indikators mit einer Aktion "zulassen"</span><span class="sxs-lookup"><span data-stu-id="7a033-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="7a033-141">Rückgängigmachen einer auf einem Gerät ausgeführten Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="7a033-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="7a033-142">Wenn eine Korrekturaktion auf einem Gerät (beispielsweise einem Windows 10-Gerät) ausgeführt wurde und das Element tatsächlich keine Bedrohung darstellt, kann Ihr Sicherheits Betriebsteam die Korrekturaktion im [Aktionscenter](mtp-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="7a033-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item is actually not a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7a033-143">Stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, bevor Sie versuchen, die folgende Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="7a033-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="7a033-144">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="7a033-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="7a033-145">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="7a033-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="7a033-146">Wählen Sie auf der Registerkarte **Verlauf** eine Aktion aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="7a033-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="7a033-147">Dadurch wird ein Flyout geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7a033-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="7a033-148">Verwenden Sie Filter, um die Ergebnisliste einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="7a033-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="7a033-149">Wählen Sie im Flyout für das ausgewählte Element die Option **Untersuchungs Seite öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="7a033-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="7a033-150">Wählen Sie in der Ansicht Details der Untersuchung die Registerkarte **Aktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="7a033-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="7a033-151">Wählen Sie ein Element mit dem Status **abgeschlossen**aus, und suchen Sie in der Spalte **Decisions** nach einem Link, beispielsweise **genehmigt**.</span><span class="sxs-lookup"><span data-stu-id="7a033-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="7a033-152">Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7a033-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="7a033-153">Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="7a033-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="7a033-154">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="7a033-154">Related articles</span></span>

- [<span data-ttu-id="7a033-155">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="7a033-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)

- [<span data-ttu-id="7a033-156">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="7a033-156">Learn more about the Action center</span></span>](mtp-action-center.md)

- [<span data-ttu-id="7a033-157">Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7a033-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

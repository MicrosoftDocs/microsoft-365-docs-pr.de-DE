---
title: Vorgehensweise Melden von falsch positiven oder falschen negativen Daten in Air in Microsoft Threat Protection
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
ms.openlocfilehash: 44c90c6c9394b1f9fee34b8eb068bb7c232c4d78
ms.sourcegitcommit: a6686a68b068adec29b72f998ac9bc95992981df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2020
ms.locfileid: "41627971"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="51390-105">Vorgehensweise Melden von falsch positiven/negativen Ergebnissen in automatisierten Ermittlungs-und Antwortfunktionen</span><span class="sxs-lookup"><span data-stu-id="51390-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="51390-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51390-106">**Applies to:**</span></span>
- <span data-ttu-id="51390-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51390-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="51390-108">Haben [automatisierte Ermittlungs-und Antwortfunktionen](mtp-autoir.md) im Microsoft Threat Protection-Vorgang fehl am oder falsch erkannt?</span><span class="sxs-lookup"><span data-stu-id="51390-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="51390-109">Es gibt Schritte, die Sie ausführen können, um es zu beheben.</span><span class="sxs-lookup"><span data-stu-id="51390-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="51390-110">Sie können:</span><span class="sxs-lookup"><span data-stu-id="51390-110">You can:</span></span>
- <span data-ttu-id="51390-111">[Melden einer falsch positiven/negativen Meldung an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="51390-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="51390-112">[Passen Sie Ihre Benachrichtigungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="51390-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="51390-113">[Rückgängigmachen von auf Geräten ausgeführten Korrekturaktionen](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="51390-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="51390-114">Verwenden Sie diesen Artikel als Leitfaden.</span><span class="sxs-lookup"><span data-stu-id="51390-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="51390-115">Melden einer falsch positiven/negativen Meldung an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="51390-115">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="51390-116">Element verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="51390-116">Item missed or wrongly detected</span></span> |<span data-ttu-id="51390-117">Dienst</span><span class="sxs-lookup"><span data-stu-id="51390-117">Service</span></span>  |<span data-ttu-id="51390-118">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="51390-118">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="51390-119">-E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="51390-119">- Email message</span></span> <br/><span data-ttu-id="51390-120">-E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="51390-120">- Email attachment</span></span> <br/><span data-ttu-id="51390-121">-URL in einer e-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="51390-121">- URL in an email message</span></span><br/><span data-ttu-id="51390-122">-URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="51390-122">- URL in an Office file</span></span>      |[<span data-ttu-id="51390-123">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51390-123">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="51390-124">Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft für Office 365-Scans</span><span class="sxs-lookup"><span data-stu-id="51390-124">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="51390-125">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="51390-125">File or app on a device</span></span>    |[<span data-ttu-id="51390-126">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51390-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="51390-127">Übermitteln einer Datei an Microsoft zur Analyse von Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="51390-127">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="51390-128">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="51390-128">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="51390-129">Szenario</span><span class="sxs-lookup"><span data-stu-id="51390-129">Scenario</span></span> |<span data-ttu-id="51390-130">Dienst</span><span class="sxs-lookup"><span data-stu-id="51390-130">Service</span></span> |<span data-ttu-id="51390-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="51390-131">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="51390-132">-Eine Warnung wird durch eine legitime Verwendung ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="51390-132">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="51390-133">-Eine Warnung ist falsch</span><span class="sxs-lookup"><span data-stu-id="51390-133">- An alert is inaccurate</span></span>    |[<span data-ttu-id="51390-134">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="51390-134">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="51390-135">oder</span><span class="sxs-lookup"><span data-stu-id="51390-135">or</span></span> <br/>[<span data-ttu-id="51390-136">Erkennung erweiterter Azure-Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="51390-136">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="51390-137">Verwalten von Benachrichtigungen im Cloud-App-Sicherheitsportal</span><span class="sxs-lookup"><span data-stu-id="51390-137">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="51390-138">Eine Datei, IP-Adresse, URL oder Domäne wird auf einem Gerät als Schadsoftware behandelt, auch wenn Sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="51390-138">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="51390-139">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51390-139">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection) |[<span data-ttu-id="51390-140">Erstellen eines benutzerdefinierten Indikators mit einer Aktion "zulassen"</span><span class="sxs-lookup"><span data-stu-id="51390-140">Create a custom indicator with an "Allow" action</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |


## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="51390-141">Rückgängigmachen einer auf einem Gerät ausgeführten Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="51390-141">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="51390-142">Wenn auf einem Gerät (beispielsweise einem Windows 10-Gerät) und dem tatsächlich sauberen Element eine Korrekturaktion ausgeführt wurde, kann Ihr Sicherheits Betriebsteam die Korrekturaktion im [Wartungscenter](mtp-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="51390-142">If a remediation action was taken on a device (such as a Windows 10 device) and the item that is actually clean, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51390-143">Stellen Sie sicher, dass Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, bevor Sie versuchen, die folgende Aufgabe auszuführen.</span><span class="sxs-lookup"><span data-stu-id="51390-143">Make sure you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) before attempting to perform the following task.</span></span>

1. <span data-ttu-id="51390-144">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="51390-144">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="51390-145">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="51390-145">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="51390-146">Wählen Sie auf der Registerkarte **Verlauf** eine Aktion aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="51390-146">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="51390-147">Dadurch wird ein Flyout geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51390-147">This opens a flyout.</span></span><br/>
    > [!TIP]
    > <span data-ttu-id="51390-148">Verwenden Sie Filter, um die Ergebnisliste einzugrenzen.</span><span class="sxs-lookup"><span data-stu-id="51390-148">Use filters to narrow down the list of results.</span></span> 

4. <span data-ttu-id="51390-149">Wählen Sie im Flyout für das ausgewählte Element die Option **Untersuchungs Seite öffnen**aus.</span><span class="sxs-lookup"><span data-stu-id="51390-149">In the flyout for the selected item, select **Open investigation page**.</span></span>

5. <span data-ttu-id="51390-150">Wählen Sie in der Ansicht Details der Untersuchung die Registerkarte **Aktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="51390-150">In the investigation details view, select the **Actions** tab.</span></span>

6. <span data-ttu-id="51390-151">Wählen Sie ein Element mit dem Status **abgeschlossen**aus, und suchen Sie in der Spalte **Decisions** nach einem Link, beispielsweise **genehmigt**.</span><span class="sxs-lookup"><span data-stu-id="51390-151">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decisions** column.</span></span> <span data-ttu-id="51390-152">Dadurch wird ein Flyout mit weiteren Details zur Aktion geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51390-152">This opens a flyout with more details about the action.</span></span>

7. <span data-ttu-id="51390-153">Um die Aktion rückgängig zu machen, wählen Sie **Korrektur löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="51390-153">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="51390-154">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="51390-154">Related articles</span></span>

- [<span data-ttu-id="51390-155">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="51390-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="51390-156">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="51390-156">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="51390-157">Proaktive Suche nach Bedrohungen mit der erweiterten Suche in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="51390-157">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)

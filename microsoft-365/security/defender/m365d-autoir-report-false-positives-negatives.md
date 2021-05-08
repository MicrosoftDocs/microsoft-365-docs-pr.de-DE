---
title: Behandeln falsch positiver oder falsch negativer Ergebnisse in AIR in Microsoft 365 Defender
description: Wurde etwas verpasst oder falsch von AIR in Microsoft 365 erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Korrektur, falsch positiv, falsch negativ
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: 727ca529dc1a16af778e01a08c9adcfe42b9b974
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245468"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="bcd57-105">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="bcd57-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bcd57-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bcd57-106">**Applies to:**</span></span>
- <span data-ttu-id="bcd57-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcd57-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="bcd57-108">Falsch positive/negative Werte können gelegentlich bei jeder Bedrohungsschutzlösung auftreten.</span><span class="sxs-lookup"><span data-stu-id="bcd57-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="bcd57-109">Wenn [automatisierte Untersuchungs- und Reaktionsfunktionen](m365d-autoir.md) in Microsoft 365 Defender etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann:</span><span class="sxs-lookup"><span data-stu-id="bcd57-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="bcd57-110">[Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="bcd57-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="bcd57-111">[Passen Sie Ihre Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="bcd57-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="bcd57-112">[Rückgängig machen von Korrekturaktionen, die auf Geräten ergriffen wurden.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="bcd57-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="bcd57-113">In den folgenden Abschnitten wird beschrieben, wie Diese Aufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bcd57-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="bcd57-114">Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="bcd57-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="bcd57-115">Element wurde verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="bcd57-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="bcd57-116">Dienst</span><span class="sxs-lookup"><span data-stu-id="bcd57-116">Service</span></span>  |<span data-ttu-id="bcd57-117">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="bcd57-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="bcd57-118">- E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="bcd57-118">- Email message</span></span> <br/><span data-ttu-id="bcd57-119">- E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="bcd57-119">- Email attachment</span></span> <br/><span data-ttu-id="bcd57-120">- URL in einer E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="bcd57-120">- URL in an email message</span></span><br/><span data-ttu-id="bcd57-121">- URL in einer Office Datei</span><span class="sxs-lookup"><span data-stu-id="bcd57-121">- URL in an Office file</span></span>      |[<span data-ttu-id="bcd57-122">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="bcd57-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="bcd57-123">Übermitteln verdächtiger Spam-, Phishing-, URLs- und Dateien an Microsoft zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="bcd57-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="bcd57-124">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="bcd57-124">File or app on a device</span></span>    |[<span data-ttu-id="bcd57-125">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bcd57-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="bcd57-126">Übermitteln einer Datei an Microsoft zur Schadsoftwareanalyse</span><span class="sxs-lookup"><span data-stu-id="bcd57-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="bcd57-127">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="bcd57-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="bcd57-128">Szenario</span><span class="sxs-lookup"><span data-stu-id="bcd57-128">Scenario</span></span> |<span data-ttu-id="bcd57-129">Dienst</span><span class="sxs-lookup"><span data-stu-id="bcd57-129">Service</span></span> |<span data-ttu-id="bcd57-130">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="bcd57-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="bcd57-131">– Eine Warnung wird durch legitime Verwendung ausgelöst</span><span class="sxs-lookup"><span data-stu-id="bcd57-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="bcd57-132">– Eine Warnung ist ungenau</span><span class="sxs-lookup"><span data-stu-id="bcd57-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="bcd57-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="bcd57-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="bcd57-134">oder</span><span class="sxs-lookup"><span data-stu-id="bcd57-134">or</span></span> <br/>[<span data-ttu-id="bcd57-135">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="bcd57-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="bcd57-136">Verwalten von Warnungen im Cloud App Security Portal</span><span class="sxs-lookup"><span data-stu-id="bcd57-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="bcd57-137">Eine Datei, eine IP-Adresse, eine URL oder eine Domäne wird auf einem Gerät als Schadsoftware behandelt, obwohl sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="bcd57-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="bcd57-138">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bcd57-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="bcd57-139">Erstellen eines benutzerdefinierten Indikators mit einer Aktion "Zulassen"</span><span class="sxs-lookup"><span data-stu-id="bcd57-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="bcd57-140">Rückgängig machen einer Korrekturaktion, die auf einem Gerät ergriffen wurde</span><span class="sxs-lookup"><span data-stu-id="bcd57-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="bcd57-141">Wenn eine Korrekturaktion für eine Entität (z. B. ein Gerät oder eine E-Mail-Nachricht) ergriffen wurde und die betroffene Entität keine bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion im [Aktionscenter](m365d-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="bcd57-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="bcd57-142">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="bcd57-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="bcd57-143">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="bcd57-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="bcd57-144">Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bcd57-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="bcd57-145">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="bcd57-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="bcd57-146">Wählen Sie im Flyoutbereich **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="bcd57-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="bcd57-147">Weitere [Informationen finden Sie unter Rückgängig gemachte Aktionen](m365d-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="bcd57-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcd57-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bcd57-148">See also</span></span>

- [<span data-ttu-id="bcd57-149">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="bcd57-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="bcd57-150">Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bcd57-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="bcd57-151">Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bcd57-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)
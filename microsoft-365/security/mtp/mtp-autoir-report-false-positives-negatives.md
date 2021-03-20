---
title: Behandeln falsch positiver oder falsch negativer Ergebnisse in AIR in Microsoft 365 Defender
description: Wurde etwas von AIR in Microsoft 365 Defender verpasst oder falsch erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
keywords: automatisiert, Untersuchung, Warnung, Korrektur, falsch positiv, falsch negativ
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
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: ccfb2c8d9395d3f64b20980b156ed51545967101
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917070"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="42113-105">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="42113-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="42113-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="42113-106">**Applies to:**</span></span>
- <span data-ttu-id="42113-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42113-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="42113-108">Falsch positive/negative Werte können gelegentlich bei jeder Bedrohungsschutzlösung auftreten.</span><span class="sxs-lookup"><span data-stu-id="42113-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="42113-109">Wenn [automatisierte Untersuchungs-](mtp-autoir.md) und Reaktionsfunktionen in Microsoft 365 Defender etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann:</span><span class="sxs-lookup"><span data-stu-id="42113-109">If [automated investigation and response capabilities](mtp-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="42113-110">[Melden eines falsch positiven/negativen Werts an Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="42113-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="42113-111">[Passen Sie Ihre Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) an (falls erforderlich); und</span><span class="sxs-lookup"><span data-stu-id="42113-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="42113-112">[Rückgängig machen von Korrekturaktionen, die auf Geräten ergriffen wurden.](#undo-a-remediation-action-that-was-taken-on-a-device)</span><span class="sxs-lookup"><span data-stu-id="42113-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="42113-113">In den folgenden Abschnitten wird beschrieben, wie Diese Aufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="42113-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="42113-114">Melden eines falsch positiven/negativen Werts an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="42113-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="42113-115">Element wurde verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="42113-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="42113-116">Dienst</span><span class="sxs-lookup"><span data-stu-id="42113-116">Service</span></span>  |<span data-ttu-id="42113-117">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="42113-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="42113-118">- E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="42113-118">- Email message</span></span> <br/><span data-ttu-id="42113-119">- E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="42113-119">- Email attachment</span></span> <br/><span data-ttu-id="42113-120">- URL in einer E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="42113-120">- URL in an email message</span></span><br/><span data-ttu-id="42113-121">- URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="42113-121">- URL in an Office file</span></span>      |[<span data-ttu-id="42113-122">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="42113-122">Microsoft Defender for Office 365</span></span>](../office-365-security/office-365-atp.md)        |[<span data-ttu-id="42113-123">Übermitteln verdächtiger Spam-, Phishing-, URLs- und Dateien an Microsoft zur Überprüfung</span><span class="sxs-lookup"><span data-stu-id="42113-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="42113-124">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="42113-124">File or app on a device</span></span>    |[<span data-ttu-id="42113-125">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="42113-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="42113-126">Übermitteln einer Datei an Microsoft zur Schadsoftwareanalyse</span><span class="sxs-lookup"><span data-stu-id="42113-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="42113-127">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="42113-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="42113-128">Szenario</span><span class="sxs-lookup"><span data-stu-id="42113-128">Scenario</span></span> |<span data-ttu-id="42113-129">Dienst</span><span class="sxs-lookup"><span data-stu-id="42113-129">Service</span></span> |<span data-ttu-id="42113-130">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="42113-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="42113-131">– Eine Warnung wird durch legitime Verwendung ausgelöst</span><span class="sxs-lookup"><span data-stu-id="42113-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="42113-132">– Eine Warnung ist ungenau</span><span class="sxs-lookup"><span data-stu-id="42113-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="42113-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="42113-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="42113-134">oder</span><span class="sxs-lookup"><span data-stu-id="42113-134">or</span></span> <br/>[<span data-ttu-id="42113-135">Azure Advanced Threat Detection</span><span class="sxs-lookup"><span data-stu-id="42113-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="42113-136">Verwalten von Warnungen im Cloud App Security-Portal</span><span class="sxs-lookup"><span data-stu-id="42113-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="42113-137">Eine Datei, eine IP-Adresse, eine URL oder eine Domäne wird auf einem Gerät als Schadsoftware behandelt, obwohl sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="42113-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="42113-138">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="42113-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="42113-139">Erstellen eines benutzerdefinierten Indikators mit einer Aktion "Zulassen"</span><span class="sxs-lookup"><span data-stu-id="42113-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="42113-140">Rückgängig machen einer Korrekturaktion, die auf einem Gerät ergriffen wurde</span><span class="sxs-lookup"><span data-stu-id="42113-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="42113-141">Wenn eine Korrekturaktion für eine Entität (z. B. ein Gerät oder eine E-Mail-Nachricht) ergriffen wurde und die betroffene Entität keine bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion im [Aktionscenter](mtp-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="42113-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](mtp-action-center.md).</span></span>

1. <span data-ttu-id="42113-142">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="42113-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="42113-143">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="42113-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="42113-144">Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="42113-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="42113-145">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="42113-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="42113-146">Wählen Sie im Flyoutbereich **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="42113-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="42113-147">Weitere [Informationen finden Sie unter Rückgängig gemachte Aktionen](mtp-autoir-actions.md#undo-completed-actions).</span><span class="sxs-lookup"><span data-stu-id="42113-147">See [Undo completed actions](mtp-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="42113-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42113-148">See also</span></span>

- [<span data-ttu-id="42113-149">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="42113-149">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="42113-150">Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42113-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="42113-151">Adress false positives/negatives in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42113-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)
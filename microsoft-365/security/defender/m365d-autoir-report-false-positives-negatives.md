---
title: Adressen falsch positiver oder falsch negativer Ergebnisse in Microsoft 365 Defender
description: Wurde etwas von AIR in Microsoft 365 Defender übersehen oder fälschlicherweise erkannt? Erfahren Sie, wie Sie falsch positive oder falsch negative Ergebnisse zur Analyse an Microsoft übermitteln.
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
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022534"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="6835d-105">Adressen falsch positiver oder falsch negativer Ergebnisse in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6835d-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6835d-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6835d-106">**Applies to:**</span></span>
- <span data-ttu-id="6835d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6835d-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="6835d-108">Bei jeder Bedrohungsschutzlösung können gelegentlich falsch positive oder negative Ergebnisse auftreten.</span><span class="sxs-lookup"><span data-stu-id="6835d-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="6835d-109">Wenn [automatisierte Untersuchungs- und Reaktionsfunktionen](m365d-autoir.md) in Microsoft 365 Defender etwas verpasst oder falsch erkannt haben, gibt es Schritte, die Ihr Sicherheitsteam ausführen kann:</span><span class="sxs-lookup"><span data-stu-id="6835d-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="6835d-110">Melden eines falsch positiven/negativen Ergebnisses an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6835d-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="6835d-111">[Anpassen der Warnungen](#adjust-an-alert-to-prevent-false-positives-from-recurring) (falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="6835d-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="6835d-112">Rückgängigmachen von Abhilfemaßnahmen, die auf Geräten durchgeführt wurden</span><span class="sxs-lookup"><span data-stu-id="6835d-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="6835d-113">In den folgenden Abschnitten wird beschrieben, wie diese Aufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6835d-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="6835d-114">Melden eines falsch positiven/negativen Ergebnisses an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="6835d-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="6835d-115">Element verpasst oder falsch erkannt</span><span class="sxs-lookup"><span data-stu-id="6835d-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="6835d-116">Dienst</span><span class="sxs-lookup"><span data-stu-id="6835d-116">Service</span></span>  |<span data-ttu-id="6835d-117">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="6835d-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="6835d-118">- E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="6835d-118">- Email message</span></span> <br/><span data-ttu-id="6835d-119">- E-Mail-Anlage</span><span class="sxs-lookup"><span data-stu-id="6835d-119">- Email attachment</span></span> <br/><span data-ttu-id="6835d-120">- URL in einer E-Mail-Nachricht</span><span class="sxs-lookup"><span data-stu-id="6835d-120">- URL in an email message</span></span><br/><span data-ttu-id="6835d-121">- URL in einer Office-Datei</span><span class="sxs-lookup"><span data-stu-id="6835d-121">- URL in an Office file</span></span>      |[<span data-ttu-id="6835d-122">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="6835d-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="6835d-123">Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien zur Überprüfung an Microsoft</span><span class="sxs-lookup"><span data-stu-id="6835d-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="6835d-124">Datei oder App auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="6835d-124">File or app on a device</span></span>    |[<span data-ttu-id="6835d-125">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6835d-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="6835d-126">Übermitteln einer Datei an Microsoft zur Schadsoftwareanalyse</span><span class="sxs-lookup"><span data-stu-id="6835d-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="6835d-127">Anpassen einer Warnung, um zu verhindern, dass falsch positive Ergebnisse wiederholt werden</span><span class="sxs-lookup"><span data-stu-id="6835d-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="6835d-128">Szenario</span><span class="sxs-lookup"><span data-stu-id="6835d-128">Scenario</span></span> |<span data-ttu-id="6835d-129">Dienst</span><span class="sxs-lookup"><span data-stu-id="6835d-129">Service</span></span> |<span data-ttu-id="6835d-130">Vorgehensweise</span><span class="sxs-lookup"><span data-stu-id="6835d-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="6835d-131">– Eine Warnung wird durch legitime Nutzung ausgelöst</span><span class="sxs-lookup"><span data-stu-id="6835d-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="6835d-132">– Eine Warnung ist ungenau</span><span class="sxs-lookup"><span data-stu-id="6835d-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="6835d-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="6835d-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="6835d-134">oder</span><span class="sxs-lookup"><span data-stu-id="6835d-134">or</span></span> <br/>[<span data-ttu-id="6835d-135">Azure Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6835d-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="6835d-136">Verwalten von Warnungen im Cloud App Security-Portal</span><span class="sxs-lookup"><span data-stu-id="6835d-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="6835d-137">Eine Datei, IP-Adresse, URL oder Domäne wird als Schadsoftware auf einem Gerät behandelt, obwohl sie sicher ist.</span><span class="sxs-lookup"><span data-stu-id="6835d-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="6835d-138">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6835d-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="6835d-139">Erstellen eines benutzerdefinierten Indikators mit einer "Zulassen"-Aktion</span><span class="sxs-lookup"><span data-stu-id="6835d-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="6835d-140">Rückgängigmachen einer Korrekturaktion, die auf einem Gerät ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="6835d-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="6835d-141">Wenn eine Korrekturmaßnahme für eine Entität (z. B. ein Gerät oder eine E-Mail-Nachricht) ausgeführt wurde und die betroffene Entität keine Bedrohung ist, kann Ihr Sicherheitsteam die Korrekturaktion im [Info-Center](m365d-action-center.md)rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="6835d-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="6835d-142">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="6835d-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="6835d-143">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="6835d-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="6835d-144">Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="6835d-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="6835d-145">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6835d-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="6835d-146">Wählen Sie im Flyoutbereich **"Rückgängig"** aus.</span><span class="sxs-lookup"><span data-stu-id="6835d-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="6835d-147">Siehe [Abgeschlossene Aktionen rückgängigmachen.](m365d-autoir-actions.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="6835d-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="6835d-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6835d-148">See also</span></span>

- [<span data-ttu-id="6835d-149">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="6835d-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="6835d-150">Proaktive Suche nach Bedrohungen mit erweiterter Suche in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6835d-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)

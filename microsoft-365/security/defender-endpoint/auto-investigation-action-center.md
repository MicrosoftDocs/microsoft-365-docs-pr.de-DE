---
title: Besuchen Sie das Aktionscenter, um Korrekturaktionen zu sehen
description: Verwenden des Aktionscenters zum Anzeigen von Details und Ergebnissen nach einer automatisierten Untersuchung
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.date: 01/28/2021
ms.technology: mde
ms.openlocfilehash: 6caa1cfe08a20aa824d85966c104a25988b8be53
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165357"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="7031f-104">Besuchen Sie das Aktionscenter, um Korrekturaktionen zu sehen</span><span class="sxs-lookup"><span data-stu-id="7031f-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="7031f-105">Während und nach einer automatisierten Untersuchung werden Abhilfemaßnahmen für Bedrohungserkennungen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7031f-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="7031f-106">Abhängig von der jeweiligen Bedrohung und der Konfiguration [von Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) für Ihre Organisation werden einige Korrekturaktionen automatisch ausgeführt, und andere erfordern eine Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="7031f-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="7031f-107">Wenn Sie Teil des Sicherheitsbetriebsteams Ihrer Organisation sind, können Sie ausstehende und abgeschlossene Korrekturaktionen [im](manage-auto-investigation.md#remediation-actions) **Aktionscenter anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="7031f-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="7031f-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7031f-108">**Applies to:**</span></span>
- [<span data-ttu-id="7031f-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7031f-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7031f-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7031f-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="7031f-111">(NEU!) Ein einheitliches Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="7031f-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="7031f-112">Wir freuen uns, ein neues, einheitliches Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="7031f-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Action Center im Microsoft 365 Security Center":::

<span data-ttu-id="7031f-114">In der folgenden Tabelle wird das neue, einheitliche Aktionscenter mit dem vorherigen Aktionscenter verglichen.</span><span class="sxs-lookup"><span data-stu-id="7031f-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="7031f-115">Das neue, einheitliche Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="7031f-115">The new, unified Action center</span></span>  |<span data-ttu-id="7031f-116">Das vorherige Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="7031f-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="7031f-117">Listet ausstehende und abgeschlossene Aktionen für Geräte und E-Mails an einem Speicherort auf.</span><span class="sxs-lookup"><span data-stu-id="7031f-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="7031f-118">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) plus Microsoft Defender for Office [365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="7031f-118">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) plus [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp))</span></span>|<span data-ttu-id="7031f-119">Listet ausstehende und abgeschlossene Aktionen für Geräte auf</span><span class="sxs-lookup"><span data-stu-id="7031f-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="7031f-120">([Nur Microsoft Defender for Endpoint)](microsoft-defender-advanced-threat-protection.md)</span><span class="sxs-lookup"><span data-stu-id="7031f-120">([Microsoft Defender for Endpoint](microsoft-defender-advanced-threat-protection.md) only)</span></span>   |
|<span data-ttu-id="7031f-121">Befindet sich unter:</span><span class="sxs-lookup"><span data-stu-id="7031f-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="7031f-122">Befindet sich unter:</span><span class="sxs-lookup"><span data-stu-id="7031f-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="7031f-123">Wählen Sie im Microsoft 365 Security Center **Aktionscenter aus.**</span><span class="sxs-lookup"><span data-stu-id="7031f-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigieren zum Action Center im Microsoft 365 Security Center"::: | <span data-ttu-id="7031f-125">Wählen Sie im Microsoft Defender Security Center das **Aktionscenter automatisierte**  >  **Untersuchungen aus.**</span><span class="sxs-lookup"><span data-stu-id="7031f-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigieren zum Aktionscenter aus dem Microsoft Defender Security Center":::  |

<span data-ttu-id="7031f-127">Das einheitliche Action Center vereint Korrekturaktionen in Defender for Endpoint und Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="7031f-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="7031f-128">Es definiert eine gemeinsame Sprache für alle Korrekturaktionen und bietet eine einheitliche Untersuchungserfahrung.</span><span class="sxs-lookup"><span data-stu-id="7031f-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="7031f-129">Sie können das einheitliche Aktionscenter verwenden, wenn Sie über entsprechende Berechtigungen und mindestens eines der folgenden Abonnements verfügen:</span><span class="sxs-lookup"><span data-stu-id="7031f-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="7031f-130">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7031f-130">Defender for Endpoint</span></span>](microsoft-defender-advanced-threat-protection.md)
- [<span data-ttu-id="7031f-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="7031f-131">Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-365-security/office-365-atp)
- [<span data-ttu-id="7031f-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7031f-132">Microsoft 365 Defender</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="7031f-133">Weitere Informationen finden Sie unter [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span><span class="sxs-lookup"><span data-stu-id="7031f-133">To learn more, see [Requirements](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="7031f-134">Verwenden des Aktionscenters</span><span class="sxs-lookup"><span data-stu-id="7031f-134">Using the Action center</span></span>

<span data-ttu-id="7031f-135">So kommen Sie zum einheitlichen Aktionscenter im verbesserten Microsoft 365 Security Center:</span><span class="sxs-lookup"><span data-stu-id="7031f-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="7031f-136">Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="7031f-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="7031f-137">Wählen Sie im Navigationsbereich **Aktionscenter aus.**</span><span class="sxs-lookup"><span data-stu-id="7031f-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="7031f-138">Wenn Sie das Aktionscenter besuchen, werden zwei Registerkarten angezeigt: **Ausstehende Aktionen** und **Verlauf**.</span><span class="sxs-lookup"><span data-stu-id="7031f-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="7031f-139">In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="7031f-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="7031f-140">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="7031f-140">Tab</span></span>  |<span data-ttu-id="7031f-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7031f-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="7031f-142">**Ausstehend**</span><span class="sxs-lookup"><span data-stu-id="7031f-142">**Pending**</span></span>     | <span data-ttu-id="7031f-143">Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="7031f-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="7031f-144">Sie können Aktionen gleichzeitig genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie denselben Aktionstyp haben (z. B. **Quarantänedatei**).</span><span class="sxs-lookup"><span data-stu-id="7031f-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="7031f-145">**TIPP:** Achten Sie darauf, ausstehende Aktionen so schnell wie möglich zu überprüfen und zu genehmigen [(oder](manage-auto-investigation.md) abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="7031f-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="7031f-146">**Verlauf**</span><span class="sxs-lookup"><span data-stu-id="7031f-146">**History**</span></span>     | <span data-ttu-id="7031f-147">Dient als Überwachungsprotokoll für Aktionen, die ergriffen wurden, z. B.:</span><span class="sxs-lookup"><span data-stu-id="7031f-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="7031f-148">– Abhilfemaßnahmen, die als Ergebnis automatisierter Untersuchungen ergriffen wurden</span><span class="sxs-lookup"><span data-stu-id="7031f-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="7031f-149">– Korrekturaktionen, die vom Sicherheitsbetriebsteam genehmigt wurden</span><span class="sxs-lookup"><span data-stu-id="7031f-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="7031f-150">– Befehle, die ausgeführt wurden, und Behebungsaktionen, die während Liveantwortsitzungen angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="7031f-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="7031f-151">– Abhilfemaßnahmen, die von Bedrohungsschutzfeatures in Microsoft Defender Antivirus ausgeführt wurden</span><span class="sxs-lookup"><span data-stu-id="7031f-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="7031f-152">Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Rückgängig gemachte Aktionen](manage-auto-investigation.md#undo-completed-actions)).</span><span class="sxs-lookup"><span data-stu-id="7031f-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="7031f-153">Sie können Daten im Aktionscenter anpassen, sortieren, filtern und exportieren.</span><span class="sxs-lookup"><span data-stu-id="7031f-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Spalten und Filter im Aktionscenter":::

- <span data-ttu-id="7031f-155">Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="7031f-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="7031f-156">Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="7031f-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="7031f-157">Wählen Sie die Spalten aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7031f-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="7031f-158">Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="7031f-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="7031f-159">Verwenden Sie Filter, um nur die Elemente zu sehen, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="7031f-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="7031f-160">Wählen **Sie Exportieren** aus, um Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="7031f-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="7031f-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7031f-161">Next steps</span></span>

- [<span data-ttu-id="7031f-162">Anzeigen und Genehmigen von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="7031f-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="7031f-163">Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Behebung von Bedrohungen mit Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7031f-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="7031f-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7031f-164">See also</span></span>

- [<span data-ttu-id="7031f-165">Adress false positives/negatives in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7031f-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)

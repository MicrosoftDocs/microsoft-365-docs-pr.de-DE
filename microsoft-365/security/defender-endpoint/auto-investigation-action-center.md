---
title: Besuchen Sie das Info-Center, um Korrekturmaßnahmen anzuzeigen.
description: Verwenden des Info-Centers zum Anzeigen von Details und Ergebnissen nach einer automatisierten Untersuchung
keywords: action, center, autoir, automated, investigation, response, remediation
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: cc806678bbb5ac19f7c4e035efb52b6ba7d1edb1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844910"
---
# <a name="visit-the-action-center-to-see-remediation-actions"></a><span data-ttu-id="9d01e-104">Besuchen Sie das Info-Center, um Korrekturmaßnahmen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d01e-104">Visit the Action center to see remediation actions</span></span>

<span data-ttu-id="9d01e-105">Während und nach einer automatisierten Untersuchung werden Korrekturaktionen für bedrohungserkennungen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="9d01e-105">During and after an automated investigation, remediation actions for threat detections are identified.</span></span> <span data-ttu-id="9d01e-106">Abhängig von der jeweiligen Bedrohung und der Konfiguration von [Microsoft Defender für Endpunkt](/windows/security/threat-protection) für Ihre Organisation werden einige Korrekturmaßnahmen automatisch ausgeführt, und andere erfordern eine Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="9d01e-106">Depending on the particular threat and how [Microsoft Defender for Endpoint](/windows/security/threat-protection) is configured for your organization, some remediation actions are taken automatically, and others require approval.</span></span> <span data-ttu-id="9d01e-107">Wenn Sie Teil des Sicherheitsteams Ihrer Organisation sind, können Sie ausstehende und abgeschlossene [Abhilfemaßnahmen](manage-auto-investigation.md#remediation-actions) im **Info-Center** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d01e-107">If you're part of your organization's security operations team, you can view pending and completed [remediation actions](manage-auto-investigation.md#remediation-actions) in the **Action center**.</span></span> 


<span data-ttu-id="9d01e-108">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9d01e-108">**Applies to:**</span></span>
- [<span data-ttu-id="9d01e-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d01e-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9d01e-110">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d01e-110">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="new-a-unified-action-center"></a><span data-ttu-id="9d01e-111">(NEU!) Ein einheitliches Info-Center</span><span class="sxs-lookup"><span data-stu-id="9d01e-111">(NEW!) A unified Action center</span></span>


<span data-ttu-id="9d01e-112">Wir freuen uns, ihnen ein neues, einheitliches Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) )!</span><span class="sxs-lookup"><span data-stu-id="9d01e-112">We are pleased to announce a new, unified Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center))!</span></span>

:::image type="content" source="images/mde-action-center-unified.png" alt-text="Info-Center im Microsoft 365 Security Center":::

<span data-ttu-id="9d01e-114">In der folgenden Tabelle wird das neue einheitliche Info-Center mit dem vorherigen Info-Center verglichen.</span><span class="sxs-lookup"><span data-stu-id="9d01e-114">The following table compares the new, unified Action center to the previous Action center.</span></span>

|<span data-ttu-id="9d01e-115">Das neue, einheitliche Info-Center</span><span class="sxs-lookup"><span data-stu-id="9d01e-115">The new, unified Action center</span></span>  |<span data-ttu-id="9d01e-116">Das vorherige Info-Center</span><span class="sxs-lookup"><span data-stu-id="9d01e-116">The previous Action center</span></span>  |
|---------|---------|
|<span data-ttu-id="9d01e-117">Listet ausstehende und abgeschlossene Aktionen für Geräte und E-Mails an einem Ort auf.</span><span class="sxs-lookup"><span data-stu-id="9d01e-117">Lists pending and completed actions for devices and email in one location</span></span> <br/><span data-ttu-id="9d01e-118">([Microsoft Defender für Endpunkt](microsoft-defender-endpoint.md) plus Microsoft Defender für [Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span><span class="sxs-lookup"><span data-stu-id="9d01e-118">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) plus [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/office-365-atp))</span></span>|<span data-ttu-id="9d01e-119">Listet ausstehende und abgeschlossene Aktionen für Geräte auf</span><span class="sxs-lookup"><span data-stu-id="9d01e-119">Lists pending and completed actions for devices</span></span> <br/> <span data-ttu-id="9d01e-120">( nur[Microsoft Defender für Endpunkt)](microsoft-defender-endpoint.md)</span><span class="sxs-lookup"><span data-stu-id="9d01e-120">([Microsoft Defender for Endpoint](microsoft-defender-endpoint.md) only)</span></span>   |
|<span data-ttu-id="9d01e-121">Befindet sich unter:</span><span class="sxs-lookup"><span data-stu-id="9d01e-121">Is located at:</span></span><br/>[https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)         |<span data-ttu-id="9d01e-122">Befindet sich unter:</span><span class="sxs-lookup"><span data-stu-id="9d01e-122">Is located at:</span></span><br/>[https://securitycenter.windows.com/action-center](https://securitycenter.windows.com/action-center)     |
| <span data-ttu-id="9d01e-123">Wählen Sie im Microsoft 365 Security Center **das Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="9d01e-123">In the Microsoft 365 security center, choose **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-new.png" alt-text="Navigieren zum Info-Center im Microsoft 365 Security Center"::: | <span data-ttu-id="9d01e-125">Wählen Sie im Microsoft Defender Security Center das  >  **Info-Center** für automatisierte Untersuchungen aus.</span><span class="sxs-lookup"><span data-stu-id="9d01e-125">In the Microsoft Defender Security Center, choose **Automated investigations** > **Action center**.</span></span> <p>:::image type="content" source="images/action-center-nav-old.png" alt-text="Navigieren zum Info-Center über die Microsoft Defender Security Center":::  |

<span data-ttu-id="9d01e-127">Das einheitliche Info-Center vereint Korrekturaktionen für Defender für Endpunkt und Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d01e-127">The unified Action center brings together remediation actions across Defender for Endpoint and Defender for Office 365.</span></span> <span data-ttu-id="9d01e-128">Es definiert eine gemeinsame Sprache für alle Korrekturmaßnahmen und bietet eine einheitliche Untersuchungserfahrung.</span><span class="sxs-lookup"><span data-stu-id="9d01e-128">It defines a common language for all remediation actions, and provides a unified investigation experience.</span></span> 

<span data-ttu-id="9d01e-129">Sie können das einheitliche Info-Center verwenden, wenn Sie über die entsprechenden Berechtigungen und eines oder mehrere der folgenden Abonnements verfügen:</span><span class="sxs-lookup"><span data-stu-id="9d01e-129">You can use the unified Action center if you have appropriate permissions and one or more of the following subscriptions:</span></span>
- [<span data-ttu-id="9d01e-130">Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d01e-130">Defender for Endpoint</span></span>](microsoft-defender-endpoint.md)
- [<span data-ttu-id="9d01e-131">Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9d01e-131">Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/office-365-atp)
- [<span data-ttu-id="9d01e-132">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d01e-132">Microsoft 365 Defender</span></span>](/microsoft-365/security/mtp/microsoft-threat-protection) 

> [!TIP]
> <span data-ttu-id="9d01e-133">Weitere Informationen finden Sie unter ["Anforderungen".](/microsoft-365/security/mtp/prerequisites)</span><span class="sxs-lookup"><span data-stu-id="9d01e-133">To learn more, see [Requirements](/microsoft-365/security/mtp/prerequisites).</span></span>

## <a name="using-the-action-center"></a><span data-ttu-id="9d01e-134">Verwenden des Info-Centers</span><span class="sxs-lookup"><span data-stu-id="9d01e-134">Using the Action center</span></span>

<span data-ttu-id="9d01e-135">So gelangen Sie zum einheitlichen Info-Center im verbesserten Microsoft 365 Security Center:</span><span class="sxs-lookup"><span data-stu-id="9d01e-135">To get to the unified Action center in the improved Microsoft 365 security center:</span></span>
1. <span data-ttu-id="9d01e-136">Wechseln Sie zum Microsoft 365 Security Center ( [https://security.microsoft.com](https://security.microsoft.com) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="9d01e-136">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="9d01e-137">Wählen Sie im Navigationsbereich **das Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="9d01e-137">In the navigation pane, select **Action center**.</span></span> 

<span data-ttu-id="9d01e-138">Wenn Sie das Info-Center besuchen, werden zwei Registerkarten angezeigt: **ausstehende Aktionen** und **Verlauf.**</span><span class="sxs-lookup"><span data-stu-id="9d01e-138">When you visit the Action center, you see two tabs: **Pending actions** and **History**.</span></span> <span data-ttu-id="9d01e-139">In der folgenden Tabelle wird zusammengefasst, was auf den einzelnen Registerkarten angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="9d01e-139">The following table summarizes what you'll see on each tab:</span></span>

|<span data-ttu-id="9d01e-140">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="9d01e-140">Tab</span></span>  |<span data-ttu-id="9d01e-141">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d01e-141">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9d01e-142">**Ausstehend**</span><span class="sxs-lookup"><span data-stu-id="9d01e-142">**Pending**</span></span>     | <span data-ttu-id="9d01e-143">Zeigt eine Liste der Aktionen an, die Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="9d01e-143">Displays a list of actions that require attention.</span></span> <span data-ttu-id="9d01e-144">Sie können Aktionen einzeln genehmigen oder ablehnen oder mehrere Aktionen auswählen, wenn sie den gleichen Aktionstyp haben (z. B. **Quarantänedatei).**</span><span class="sxs-lookup"><span data-stu-id="9d01e-144">You can approve or reject actions one at a time, or select multiple actions if they have the same type of action (such as **Quarantine file**).</span></span> <br/><span data-ttu-id="9d01e-145">**TIPP:** Stellen Sie sicher, dass ausstehende Aktionen so schnell wie möglich [überprüft und genehmigt (oder abgelehnt)](manage-auto-investigation.md) werden, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="9d01e-145">**TIP**: Make sure to [review and approve (or reject) pending actions](manage-auto-investigation.md) as soon as possible so that your automated investigations can complete in a timely manner.</span></span> |
|<span data-ttu-id="9d01e-146">**Verlauf**</span><span class="sxs-lookup"><span data-stu-id="9d01e-146">**History**</span></span>     | <span data-ttu-id="9d01e-147">Dient als Überwachungsprotokoll für ausgeführte Aktionen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="9d01e-147">Serves as an audit log for actions that were taken, such as:</span></span> <br/><span data-ttu-id="9d01e-148">– Korrekturmaßnahmen, die als Ergebnis automatisierter Untersuchungen durchgeführt wurden</span><span class="sxs-lookup"><span data-stu-id="9d01e-148">- Remediation actions that were taken as a result of automated investigations</span></span> <br><span data-ttu-id="9d01e-149">– Abhilfemaßnahmen, die von Ihrem Sicherheitsteam genehmigt wurden</span><span class="sxs-lookup"><span data-stu-id="9d01e-149">- Remediation actions that were approved by your security operations team</span></span>  <br/><span data-ttu-id="9d01e-150">– Befehle, die ausgeführt wurden, und Korrekturaktionen, die während der Live Response-Sitzungen angewendet wurden</span><span class="sxs-lookup"><span data-stu-id="9d01e-150">- Commands that were run and remediation actions that were applied during Live Response sessions</span></span>  <br/><span data-ttu-id="9d01e-151">– Abhilfemaßnahmen, die von Bedrohungsschutzfeatures in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="9d01e-151">- Remediation actions that were taken by threat protection features in Microsoft Defender Antivirus</span></span>  <p><span data-ttu-id="9d01e-152">Bietet eine Möglichkeit, bestimmte Aktionen rückgängig zu machen (siehe [Abgeschlossene Aktionen rückgängig machen).](manage-auto-investigation.md#undo-completed-actions)</span><span class="sxs-lookup"><span data-stu-id="9d01e-152">Provides a way to undo certain actions (see [Undo completed actions](manage-auto-investigation.md#undo-completed-actions)).</span></span>       |

<span data-ttu-id="9d01e-153">Sie können Daten im Info-Center anpassen, sortieren, filtern und exportieren.</span><span class="sxs-lookup"><span data-stu-id="9d01e-153">You can customize, sort, filter, and export data in the Action center.</span></span>

:::image type="content" source="images/new-action-center-columnsfilters.png" alt-text="Spalten und Filter im Info-Center":::

- <span data-ttu-id="9d01e-155">Wählen Sie eine Spaltenüberschrift aus, um Elemente in aufsteigender oder absteigender Reihenfolge zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="9d01e-155">Select a column heading to sort items in ascending or descending order.</span></span>
- <span data-ttu-id="9d01e-156">Verwenden Sie den Zeitraumfilter, um Daten für den letzten Tag, die letzte Woche, 30 Tage oder 6 Monate anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9d01e-156">Use the time period filter to view data for the past day, week, 30 days, or 6 months.</span></span>
- <span data-ttu-id="9d01e-157">Wählen Sie die Spalten aus, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="9d01e-157">Choose the columns that you want to view.</span></span>
- <span data-ttu-id="9d01e-158">Geben Sie an, wie viele Elemente auf jeder Datenseite enthalten sein sollen.</span><span class="sxs-lookup"><span data-stu-id="9d01e-158">Specify how many items to include on each page of data.</span></span>
- <span data-ttu-id="9d01e-159">Verwenden Sie Filter, um nur die Elemente anzuzeigen, die Sie sehen möchten.</span><span class="sxs-lookup"><span data-stu-id="9d01e-159">Use filters to view just the items you want to see.</span></span>
- <span data-ttu-id="9d01e-160">Wählen Sie **"Exportieren"** aus, um Ergebnisse in eine .csv Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="9d01e-160">Select **Export** to export results to a .csv file.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="9d01e-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9d01e-161">Next steps</span></span>

- [<span data-ttu-id="9d01e-162">Anzeigen und Genehmigen von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="9d01e-162">View and approve remediation actions</span></span>](manage-auto-investigation.md)
- [<span data-ttu-id="9d01e-163">Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Beheben von Bedrohungen mit Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d01e-163">See the interactive guide: Investigate and remediate threats with Microsoft Defender for Endpoint</span></span>](https://aka.ms/MDATP-IR-Interactive-Guide)
 
## <a name="see-also"></a><span data-ttu-id="9d01e-164">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9d01e-164">See also</span></span>

- [<span data-ttu-id="9d01e-165">Adressiert falsch positive/negative Ergebnisse in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9d01e-165">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](defender-endpoint-false-positives-negatives.md)

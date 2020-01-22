---
title: Anzeigen der Details und Ergebnisse einer automatischen Untersuchung
description: Während und nach einer automatischen Untersuchung können Sie die Ergebnisse und die wichtigsten Erkenntnisse anzeigen.
keywords: automatisch, Untersuchungen, Ergebnisse, analysieren, Details, Behebung, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: e70fa5f226b25df72514f75bb20873665d9021f6
ms.sourcegitcommit: ca06ee52dec472d3827983d67b049847ec2fdfc1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2020
ms.locfileid: "41256551"
---
# <a name="view-the-details-and-results-of-an-automated-investigation"></a><span data-ttu-id="02422-104">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="02422-104">View the details and results of an automated investigation</span></span>

<span data-ttu-id="02422-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="02422-105">**Applies to:**</span></span>
- <span data-ttu-id="02422-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="02422-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="02422-107">Wenn eine automatische Untersuchung in Microsoft Threat Protection stattfindet, stehen während und nach der automatischen Ermittlung Details zu dieser Untersuchung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="02422-107">When an automated investigation occurs in Microsoft Threat Protection, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="02422-108">Wenn Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen.</span><span class="sxs-lookup"><span data-stu-id="02422-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="02422-109">Die Anzeige mit Untersuchungsdetails bieten Ihnen den aktuellen Status sowie die Möglichkeit, ausstehende Aktionen zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="02422-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Untersuchungsdetails](../images/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="02422-111">Öffnen der Anzeige mit Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="02422-111">Open the investigation details view</span></span>

<span data-ttu-id="02422-112">Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:</span><span class="sxs-lookup"><span data-stu-id="02422-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="02422-113">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="02422-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="02422-114">Auswählen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="02422-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="02422-115">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="02422-115">Select an item in the Action center</span></span>

<span data-ttu-id="02422-116">Verwenden Sie das Info-Center, um Aktionen anzuzeigen, deren Genehmigung aussteht (auf der Registerkarte **Ausstehend**) oder die bereits genehmigt wurden (auf der Registerkarte **Verlauf**).</span><span class="sxs-lookup"><span data-stu-id="02422-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="02422-117">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="02422-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="02422-118">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="02422-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="02422-119">Wählen Sie auf der Registerkarte **Ausstehend** oder **Verlauf** ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="02422-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="02422-120">Wenn Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie ausstehende Aktionen genehmigen (oder ablehnen).</span><span class="sxs-lookup"><span data-stu-id="02422-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="02422-121">Öffnen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="02422-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="02422-122">Verwenden Sie die Seite „Vorfalldetails“, um detaillierte Informationen zu einem Vorfall anzuzeigen, einschließlich ausgelöster Warnungen und Informationen zu betroffenen Geräten, Benutzerkonten oder Postfächern.</span><span class="sxs-lookup"><span data-stu-id="02422-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="02422-123">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="02422-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="02422-124">Wählen Sie im Navigationsbereich **Vorfälle** aus.</span><span class="sxs-lookup"><span data-stu-id="02422-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="02422-125">Wählen Sie ein Element in der Liste aus, um die Vorfalldetailsseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="02422-125">Select an item in the list to open the incident details view.</span></span><br/>![Vorfalldetails](../images/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="02422-127">Wählen Sie auf der Registerkarte **Untersuchung** eine Untersuchung in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="02422-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="02422-128">Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="02422-128">Investigation details</span></span>

<span data-ttu-id="02422-129">Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="02422-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="02422-130">Die Anzeige mit Untersuchungsdetails sieht wie in der folgenden Abbildung aus:</span><span class="sxs-lookup"><span data-stu-id="02422-130">The investigation details view resembles the following image:</span></span>

![Untersuchungsdetails](../images/mtp-air-investdetails.png)

<span data-ttu-id="02422-132">In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen**, **Geräte**, **Identitäten**, **Wichtige Erkenntnisse**, **Entitäten**, **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="02422-132">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="02422-133">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="02422-133">Tab</span></span>    |<span data-ttu-id="02422-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="02422-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="02422-135">Untersuchungsdiagramm</span><span class="sxs-lookup"><span data-stu-id="02422-135">Investigation graph</span></span>    |<span data-ttu-id="02422-136">Bietet eine visuelle Darstellung der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="02422-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="02422-137">Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="02422-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="02422-138">Sie können auf ein Element im Diagramm klicken, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="02422-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="02422-139">Wenn Sie beispielsweise auf das Symbol **Bedrohungen gefunden** klicken, gelangen Sie zur Registerkarte **Wichtige Erkenntnisse**.</span><span class="sxs-lookup"><span data-stu-id="02422-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="02422-140">Warnungen</span><span class="sxs-lookup"><span data-stu-id="02422-140">Alerts</span></span> |<span data-ttu-id="02422-141">Listet die mit der Untersuchung verbundenen Warnungen auf.</span><span class="sxs-lookup"><span data-stu-id="02422-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="02422-142">Warnungen können aus den Features zum Schutz vor Bedrohungen auf dem Computer eines Benutzers, aus Office-Apps, aus Cloud App Security und aus anderen Features von Microsoft 365 Threat Protection stammen.</span><span class="sxs-lookup"><span data-stu-id="02422-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="02422-143">Geräte</span><span class="sxs-lookup"><span data-stu-id="02422-143">Devices</span></span>|<span data-ttu-id="02422-144">Listet die in die Untersuchung einbezogenen Computer zusammen mit der Korrekturstufe auf.</span><span class="sxs-lookup"><span data-stu-id="02422-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="02422-145">Wichtige Erkenntnisse</span><span class="sxs-lookup"><span data-stu-id="02422-145">Key findings</span></span>   |<span data-ttu-id="02422-146">Listet die Ergebnisse der Untersuchung sowie den Status und die ausgeführten oder ausstehenden Aktionen auf.</span><span class="sxs-lookup"><span data-stu-id="02422-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="02422-147">Sie können ausstehende Aktionen für Geräte und Identitäten auf dieser Registerkarte genehmigen.</span><span class="sxs-lookup"><span data-stu-id="02422-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="02422-148">Entitäten</span><span class="sxs-lookup"><span data-stu-id="02422-148">Entities</span></span>   |<span data-ttu-id="02422-149">Listet Benutzeraktivitäten, Dateien, Prozesse, Dienste, Treiber, IP-Adressen und Persistenzverfahren im Zusammenhang mit der Untersuchung zusammen mit dem Status und ausgeführten Aktionen auf.</span><span class="sxs-lookup"><span data-stu-id="02422-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="02422-150">Protokoll</span><span class="sxs-lookup"><span data-stu-id="02422-150">Log</span></span>    |<span data-ttu-id="02422-151">Bietet eine detaillierte Darstellung aller während der Untersuchung ausgeführten Schritte zusammen mit dem Status.</span><span class="sxs-lookup"><span data-stu-id="02422-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="02422-152">Ausstehende Aktionen</span><span class="sxs-lookup"><span data-stu-id="02422-152">Pending actions</span></span>    |<span data-ttu-id="02422-153">Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="02422-153">Lists items that require approval to proceed.</span></span>|

## <a name="remediation-actions-following-automated-investigation"></a><span data-ttu-id="02422-154">Korrekturaktionen nach einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="02422-154">Remediation actions following automated investigation</span></span>

<span data-ttu-id="02422-155">Wenn eine automatische Untersuchung abgeschlossen ist, wird für alle beteiligten Beweise eine Erkenntnis ermittelt, und es werden Korrekturaktionen identifiziert.</span><span class="sxs-lookup"><span data-stu-id="02422-155">When an automated investigation completes, a verdict is reached for every piece of evidence involved, and remediation actions are identified.</span></span> <span data-ttu-id="02422-156">In einigen Fällen werden Korrekturaktionen automatisch ausgeführt. In anderen Fällen müssen Korrekturaktionen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="02422-156">In some cases, remediation actions are taken automatically; in other cases, remediation actions await approval.</span></span> <span data-ttu-id="02422-157">In der folgenden Tabelle sind mögliche Urteile und Ergebnisse aufgelistet:</span><span class="sxs-lookup"><span data-stu-id="02422-157">The following table lists possible verdicts and outcomes:</span></span>

|<span data-ttu-id="02422-158">Erkenntnis</span><span class="sxs-lookup"><span data-stu-id="02422-158">Verdict</span></span>    |<span data-ttu-id="02422-159">Bereich</span><span class="sxs-lookup"><span data-stu-id="02422-159">Area</span></span>   |<span data-ttu-id="02422-160">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="02422-160">Outcomes</span></span>|
|------|------|------|
|<span data-ttu-id="02422-161">Bösartig</span><span class="sxs-lookup"><span data-stu-id="02422-161">Malicious</span></span>  |<span data-ttu-id="02422-162">Geräte (Endpunkte)</span><span class="sxs-lookup"><span data-stu-id="02422-162">Devices (endpoints)</span></span>    |<span data-ttu-id="02422-163">Korrekturaktionen werden automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="02422-163">Remediation actions are taken automatically</span></span>|
|<span data-ttu-id="02422-164">Bösartig</span><span class="sxs-lookup"><span data-stu-id="02422-164">Malicious</span></span>  |<span data-ttu-id="02422-165">E-Mail-Inhalt (URLs oder Anlagen)</span><span class="sxs-lookup"><span data-stu-id="02422-165">Email content (URLs or attachments)</span></span> | <span data-ttu-id="02422-166">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="02422-166">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="02422-167">Verdächtig</span><span class="sxs-lookup"><span data-stu-id="02422-167">Suspicious</span></span> |<span data-ttu-id="02422-168">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="02422-168">Devices or email content</span></span> |<span data-ttu-id="02422-169">Empfohlene Korrekturaktionen müssen genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="02422-169">Recommended remediation actions are pending approval</span></span>|
|<span data-ttu-id="02422-170">Bereinigen</span><span class="sxs-lookup"><span data-stu-id="02422-170">Clean</span></span>  |<span data-ttu-id="02422-171">Geräte oder E-Mail-Inhalte</span><span class="sxs-lookup"><span data-stu-id="02422-171">Devices or email content</span></span>   |<span data-ttu-id="02422-172">Es sind keine Korrekturaktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="02422-172">No remediation actions are needed</span></span>|

[<span data-ttu-id="02422-173">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="02422-173">Review a pending action in the Action center</span></span>](mtp-autoir-actions.md#review-a-pending-action-in-the-action-center)

> [!TIP]
> <span data-ttu-id="02422-174">Wenn Sie glauben, dass durch automatisierte Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection etwas übersehen oder fälschlicherweise erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="02422-174">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft Threat Protection, let us know!</span></span> <span data-ttu-id="02422-175">Weitere Informationen finden Sie unter [How to Report false positives/negatives in Automated Investigation and Response (Air) Funktionen in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span><span class="sxs-lookup"><span data-stu-id="02422-175">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft Threat Protection](mtp-autoir-report-false-positives-negatives.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="02422-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="02422-176">Next steps</span></span>

- [<span data-ttu-id="02422-177">Abrufen einer Übersicht über die Berechtigungen im Info-Center</span><span class="sxs-lookup"><span data-stu-id="02422-177">Get an overview of Action center permissions</span></span>](mtp-action-center.md#required-permissions-for-action-center-tasks)
- [<span data-ttu-id="02422-178">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="02422-178">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)


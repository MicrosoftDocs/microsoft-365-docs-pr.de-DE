---
title: Details und Ergebnisse einer automatisierten Untersuchung
description: Anzeigen der Ergebnisse und wichtigsten Ergebnisse der automatisierten Untersuchung in Microsoft 365 Defender
keywords: automatisch, Untersuchungen, Ergebnisse, analysieren, Details, Behebung, autoair
search.appverid: met150
ms.prod: m365-security
ms.technology: m365d
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
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.openlocfilehash: 2cc83e24d4dd81c9d2e972fa274b48fc3946532a
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289727"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="c8ae3-104">Details und Ergebnisse einer automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="c8ae3-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c8ae3-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-105">**Applies to:**</span></span>
- <span data-ttu-id="c8ae3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c8ae3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c8ae3-107">Mit Microsoft 365 Defender, wenn eine [automatisierte Untersuchung](m365d-autoir.md) ausgeführt wird, sind Details zu dieser Untersuchung sowohl während als auch nach dem automatisierten Untersuchungsprozess verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-107">With Microsoft 365 Defender, when an [automated investigation](m365d-autoir.md) runs, details about that investigation are available both during and after the automated investigation process.</span></span> <span data-ttu-id="c8ae3-108">Wenn Sie über die [erforderlichen Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-108">If you have the [necessary permissions](m365d-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="c8ae3-109">Diese Ansicht bietet Ihnen den aktuellen Status und die Möglichkeit, alle ausstehenden Aktionen zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-109">This view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Untersuchungsdetails":::

## <a name="new-unified-investigation-page"></a><span data-ttu-id="c8ae3-111">(NEU!) Einheitliche Untersuchungsseite</span><span class="sxs-lookup"><span data-stu-id="c8ae3-111">(NEW!) Unified investigation page</span></span>

<span data-ttu-id="c8ae3-112">Die Untersuchungsseite wurde kürzlich aktualisiert, um Informationen über Ihre Geräte, E-Mails und Zusammenarbeitsinhalte hinweg einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-112">The investigation page has recently been updated to include information across your devices, email, and collaboration content.</span></span> <span data-ttu-id="c8ae3-113">Die neue, einheitliche Untersuchungsseite definiert eine gemeinsame Sprache und bietet eine einheitliche Oberfläche für automatische Untersuchungen in [Microsoft Defender für Endpunkt](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) und Microsoft Defender für [Office 365.](../office-365-security/defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c8ae3-113">The new, unified investigation page defines a common language and provides a unified experience for automatic investigations across [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) and [Microsoft Defender for Office 365](../office-365-security/defender-for-office-365.md).</span></span> <span data-ttu-id="c8ae3-114">Um auf die einheitliche Untersuchungsseite zuzugreifen, wählen Sie den Link im gelben Banner aus, auf dem Sie sehen werden:</span><span class="sxs-lookup"><span data-stu-id="c8ae3-114">To access the unified investigation page, select the link in the yellow banner you'll see on:</span></span>

- <span data-ttu-id="c8ae3-115">Jede Untersuchungsseite im Office 365 Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) )</span><span class="sxs-lookup"><span data-stu-id="c8ae3-115">Any investigation page in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com))</span></span>
- <span data-ttu-id="c8ae3-116">Jede Untersuchungsseite im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )</span><span class="sxs-lookup"><span data-stu-id="c8ae3-116">Any investigation page in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))</span></span>
- <span data-ttu-id="c8ae3-117">Jede Vorfall- oder Info-Center-Erfahrung im Microsoft 365 Defender-Portal ( [https://security.microsoft.com](https://security.microsoft.com) )</span><span class="sxs-lookup"><span data-stu-id="c8ae3-117">Any incident or Action center experience in the Microsoft 365 Defender portal ([https://security.microsoft.com](https://security.microsoft.com))</span></span>

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="c8ae3-118">Öffnen der Anzeige mit Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="c8ae3-118">Open the investigation details view</span></span>

<span data-ttu-id="c8ae3-119">Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:</span><span class="sxs-lookup"><span data-stu-id="c8ae3-119">You can open the investigation details view by using one of the following methods:</span></span>

- [<span data-ttu-id="c8ae3-120">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="c8ae3-120">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="c8ae3-121">Auswählen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="c8ae3-121">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="c8ae3-122">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="c8ae3-122">Select an item in the Action center</span></span>

<span data-ttu-id="c8ae3-123">Das verbesserte [Info-Center](m365d-action-center.md) ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) vereint [Korrekturaktionen](m365d-remediation-actions.md) auf Ihren Geräten, E-Mails & Inhalte für die Zusammenarbeit und Identitäten.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-123">The improved [Action center](m365d-action-center.md) ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) brings together [remediation actions](m365d-remediation-actions.md) across your devices, email & collaboration content, and identities.</span></span> <span data-ttu-id="c8ae3-124">Zu den aufgeführten Aktionen gehören Wartungsaktionen, die automatisch oder manuell durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-124">Listed actions include remediation actions that were taken automatically or manually.</span></span> <span data-ttu-id="c8ae3-125">Im Info-Center können Sie Aktionen anzeigen, die auf die Genehmigung warten, und Aktionen, die bereits genehmigt oder abgeschlossen wurden.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-125">In the Action center, you can view actions that are awaiting approval and actions that were already approved or completed.</span></span> <span data-ttu-id="c8ae3-126">Sie können auch zu weiteren Details navigieren, z. B. zu einer Untersuchungsseite.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-126">You can also navigate to more details, such as an investigation page.</span></span>

> [!TIP]
> <span data-ttu-id="c8ae3-127">Sie müssen [über bestimmte Berechtigungen](m365d-action-center.md#required-permissions-for-action-center-tasks) verfügen, um Aktionen zu genehmigen, abzulehnen oder rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-127">You must have [certain permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve, reject, or undo actions.</span></span>

1. <span data-ttu-id="c8ae3-128">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-128">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="c8ae3-129">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-129">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="c8ae3-130">Wählen Sie auf der Registerkarte **Ausstehend** oder **Verlauf** ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-130">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="c8ae3-131">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-131">Its flyout pane opens.</span></span>

4. <span data-ttu-id="c8ae3-132">Überprüfen Sie die Informationen im Flyoutbereich, und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="c8ae3-132">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="c8ae3-133">Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-133">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="c8ae3-134">Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-134">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="c8ae3-135">Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-135">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="c8ae3-136">Wählen Sie **"Gehe Auf Suche"** aus, um zur [erweiterten Suche](advanced-hunting-overview.md)zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-136">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="c8ae3-137">Öffnen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="c8ae3-137">Open an investigation from an incident details page</span></span>

<span data-ttu-id="c8ae3-138">Verwenden Sie die Seite „Vorfalldetails“, um detaillierte Informationen zu einem Vorfall anzuzeigen, einschließlich ausgelöster Warnungen und Informationen zu betroffenen Geräten, Benutzerkonten oder Postfächern.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-138">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="c8ae3-139">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-139">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="c8ae3-140">Wählen Sie im Navigationsbereich **Vorfälle &**  >  **Warnungsvorfälle** aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-140">In the navigation pane, choose **Incidents & alerts** > **Incidents**.</span></span> 

3. <span data-ttu-id="c8ae3-141">Wählen Sie ein Element in der Liste aus, und wählen Sie dann die **Seite "Vorfall öffnen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-141">Select an item in the list, and then choose **Open incident page**.</span></span>

4. <span data-ttu-id="c8ae3-142">Wählen Sie die Registerkarte **"Untersuchungen"** aus, und wählen Sie dann eine Untersuchung in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-142">Select the **Investigations** tab, and then select an investigation in the list.</span></span> <span data-ttu-id="c8ae3-143">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-143">Its flyout pane opens.</span></span>

5. <span data-ttu-id="c8ae3-144">Wählen Sie **die Seite "Untersuchung öffnen"** aus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-144">Select **Open investigation page**.</span></span> 

<span data-ttu-id="c8ae3-145">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-145">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-incidentdetails-tabs.png" alt-text="Vorfalldetails":::

## <a name="investigation-details"></a><span data-ttu-id="c8ae3-147">Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="c8ae3-147">Investigation details</span></span>

<span data-ttu-id="c8ae3-148">Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-148">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="c8ae3-149">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-149">Here's an example.</span></span>

:::image type="content" source="../../media/mtp-air-investdetails.png" alt-text="Untersuchungsdetails":::

<span data-ttu-id="c8ae3-151">In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen**, **Geräte**, **Identitäten**, **Wichtige Erkenntnisse**, **Entitäten**, **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-151">In the Investigation details view, you can see information on the **Investigation graph**, **Alerts**, **Devices**, **Identities**, **Key findings**, **Entities**, **Log**, and **Pending actions** tabs, described in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="c8ae3-152">Welche Registerkarten auf einer Untersuchungsdetailseite angezeigt werden, hängt davon ab, was Ihr Abonnement enthält.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-152">The specific tabs you see in an investigation details page depends on what your subscription includes.</span></span> <span data-ttu-id="c8ae3-153">Wenn Ihr Abonnement beispielsweise Microsoft Defender für Office 365 Plan 2 nicht enthält, wird keine Registerkarte **"Postfächer"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-153">For example, if your subscription does not include Microsoft Defender for Office 365 Plan 2, you won't see a **Mailboxes** tab.</span></span>

| <span data-ttu-id="c8ae3-154">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="c8ae3-154">Tab</span></span> | <span data-ttu-id="c8ae3-155">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c8ae3-155">Description</span></span> |
|:--------|:--------|
| <span data-ttu-id="c8ae3-156">**Untersuchungsdiagramm**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-156">**Investigation graph**</span></span> | <span data-ttu-id="c8ae3-157">Bietet eine visuelle Darstellung der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-157">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="c8ae3-158">Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-158">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="c8ae3-159">Sie können ein Element im Diagramm auswählen, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-159">You can select an item on the graph to view more details.</span></span> <span data-ttu-id="c8ae3-160">Wenn Sie z. B. das **Symbol "Nachweis"** auswählen, gelangen Sie zur Registerkarte **"Nachweis",** auf der Sie erkannte Entitäten und deren Bewertungen sehen können.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-160">For example, selecting the **Evidence** icon takes you to the **Evidence** tab, where you can see detected entities and their verdicts.</span></span> |
| <span data-ttu-id="c8ae3-161">**Benachrichtigungen**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-161">**Alerts**</span></span> | <span data-ttu-id="c8ae3-162">Listet die mit der Untersuchung verbundenen Warnungen auf.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-162">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="c8ae3-163">Warnungen können von Bedrohungsschutzfeatures auf dem Gerät eines Benutzers, in Office Apps, Microsoft Cloud App Security und anderen Microsoft 365 Defender Features stammen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-163">Alerts can come from threat protection features on a user's device, in Office apps, Microsoft Cloud App Security, and other Microsoft 365 Defender features.</span></span>|
| <span data-ttu-id="c8ae3-164">**Geräte**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-164">**Devices**</span></span> | <span data-ttu-id="c8ae3-165">Listet die in der Untersuchung enthaltenen Geräte zusammen mit deren Korrekturstufe auf.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-165">Lists devices included in the investigation along with their remediation level.</span></span> <span data-ttu-id="c8ae3-166">(Korrekturstufen entsprechen [der Automatisierungsstufe für Gerätegruppen.)](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups)</span><span class="sxs-lookup"><span data-stu-id="c8ae3-166">(Remediation levels correspond to [the automation level for device groups](m365d-configure-auto-investigation-response.md#review-or-change-the-automation-level-for-device-groups).)</span></span> |
| <span data-ttu-id="c8ae3-167">**Postfächer**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-167">**Mailboxes**</span></span> |<span data-ttu-id="c8ae3-168">Listet Postfächer auf, die von erkannten Bedrohungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-168">Lists mailboxes that are impacted by detected threats.</span></span>  |
| <span data-ttu-id="c8ae3-169">**Benutzer**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-169">**Users**</span></span>  | <span data-ttu-id="c8ae3-170">Listet Benutzerkonten auf, die von erkannten Bedrohungen betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-170">Lists user accounts that are impacted by detected threats.</span></span> |
| <span data-ttu-id="c8ae3-171">**Beweise**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-171">**Evidence**</span></span> | <span data-ttu-id="c8ae3-172">Listet Nachweise auf, die durch Warnungen oder Untersuchungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-172">Lists pieces of evidence raised by alerts or investigations.</span></span> <span data-ttu-id="c8ae3-173">Umfasst Bewertungen (*bösartig*, *verdächtig,* *unbekannt* oder *keine Bedrohungen gefunden*) und Den Wartungsstatus.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-173">Includes verdicts (*Malicious*, *Suspicious*, *Unknown*, or *No threats found*) and remediation status.</span></span> |
| <span data-ttu-id="c8ae3-174">**Entities**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-174">**Entities**</span></span> | <span data-ttu-id="c8ae3-175">Enthält Details zu jeder analysierten Entität, einschließlich einer Bewertung für jeden Entitätstyp (*Bösartig,* *Verdächtig* oder *keine Bedrohungen gefunden*).</span><span class="sxs-lookup"><span data-stu-id="c8ae3-175">Provides details about each analyzed entity, including a verdict for each entity type (*Malicious*, *Suspicious*, or *No threats found*).</span></span>|
|<span data-ttu-id="c8ae3-176">**Log**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-176">**Log**</span></span> | <span data-ttu-id="c8ae3-177">Bietet eine chronologische, detaillierte Ansicht aller Untersuchungsaktionen, die nach dem Auslösen einer Warnung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-177">Provides a chronological, detailed view of all the investigation actions taken after an alert was triggered.</span></span>|
| <span data-ttu-id="c8ae3-178">**Verlauf ausstehender Aktionen**</span><span class="sxs-lookup"><span data-stu-id="c8ae3-178">**Pending actions history**</span></span> | <span data-ttu-id="c8ae3-179">Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-179">Lists items that require approval to proceed.</span></span> <span data-ttu-id="c8ae3-180">Wechseln Sie zum Info-Center ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), um ausstehende Aktionen zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="c8ae3-180">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) to approve pending actions.</span></span> |

## <a name="next-steps"></a><span data-ttu-id="c8ae3-181">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c8ae3-181">Next steps</span></span>

- [<span data-ttu-id="c8ae3-182">Anzeigen und Genehmigen von Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="c8ae3-182">View and manage remediation actions</span></span>](m365d-autoir-actions.md)
- [<span data-ttu-id="c8ae3-183">Weitere Informationen zu Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="c8ae3-183">Learn more about remediation actions</span></span>](m365d-remediation-actions.md)

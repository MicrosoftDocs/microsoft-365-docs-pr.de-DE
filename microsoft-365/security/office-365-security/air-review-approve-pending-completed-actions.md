---
title: Überprüfen und Verwalten von Abhilfemaßnahmen in Microsoft Defender für Office 365
keywords: AIR, autoIR, Microsoft Defender für Endpunkt, automatisiert, Untersuchung, Reaktion, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie mehr über Abhilfemaßnahmen in automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108535"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="4b9b6-104">Überprüfen und Verwalten von Korrekturmaßnahmen in Office 365</span><span class="sxs-lookup"><span data-stu-id="4b9b6-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="4b9b6-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="4b9b6-105">**Applies to**</span></span>
- [<span data-ttu-id="4b9b6-106">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="4b9b6-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)

<span data-ttu-id="4b9b6-107">Da automatisierte Untersuchungen an E-Mail-& Inhalten für die Zusammenarbeit zu Bewertungen führen, z. B. *bösartig* oder *verdächtig,* werden bestimmte Abhilfemaßnahmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-107">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="4b9b6-108">In Microsoft Defender für Office 365 können Korrekturaktionen Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="4b9b6-108">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="4b9b6-109">Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern</span><span class="sxs-lookup"><span data-stu-id="4b9b6-109">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="4b9b6-110">Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="4b9b6-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="4b9b6-111">Diese Korrekturmaßnahmen werden erst ausgeführt, wenn sie von Ihrem Sicherheitsteam genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="4b9b6-112">Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="4b9b6-113">In einigen Fällen können Sie eingereichte Aktionen erneut prüfen.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-113">In some cases, you can reconsider submitted actions.</span></span>  <span data-ttu-id="4b9b6-114">Sie müssen Teil der Rolle "Suchen & Löschen" sein, bevor Sie Aktionen ausführen.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-114">You need to be part of Search & purge role before taking any actions.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="4b9b6-115">Genehmigen (oder Ablehnen) ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="4b9b6-115">Approve (or reject) pending actions</span></span>
<span data-ttu-id="4b9b6-116">Es gibt vier verschiedene Möglichkeiten, automatische Untersuchungsaktionen zu finden und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="4b9b6-116">There are four different ways to find and take auto investigation actions:</span></span>

- [<span data-ttu-id="4b9b6-117">Vorfallwarteschlange</span><span class="sxs-lookup"><span data-stu-id="4b9b6-117">Incident queue</span></span>](https://security.microsoft.com/incidents)
- [<span data-ttu-id="4b9b6-118">Info-Center</span><span class="sxs-lookup"><span data-stu-id="4b9b6-118">Action center</span></span>](https://security.microsoft.com/action-center/pending)
- <span data-ttu-id="4b9b6-119">Untersuchung selbst (Zugriff über Vorfall oder über eine Warnung)</span><span class="sxs-lookup"><span data-stu-id="4b9b6-119">Investigation itself (accessed via Incident or from an alert)</span></span>
- [<span data-ttu-id="4b9b6-120">Untersuchungs- und Korrekturuntersuchungen in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="4b9b6-120">Investigation and remediation investigations queue</span></span>](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a><span data-ttu-id="4b9b6-121">Vorfallwarteschlange</span><span class="sxs-lookup"><span data-stu-id="4b9b6-121">Incident queue</span></span>

1. <span data-ttu-id="4b9b6-122">Öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-122">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-123">Wählen Sie im Navigationsbereich **Vorfälle & Warnungen > Vorfälle aus.**</span><span class="sxs-lookup"><span data-stu-id="4b9b6-123">In the navigation pane, select **Incidents & alerts > Incidents**.</span></span>
3. <span data-ttu-id="4b9b6-124">Wählen Sie einen Vorfallnamen aus, um die Zusammenfassungsseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-124">Select an incident name to open its summary page.</span></span>
4. <span data-ttu-id="4b9b6-125">Wählen Sie die Registerkarte **"Nachweise und Antwort"** aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-125">Select the **Evidence and Response** tab.</span></span>
5. <span data-ttu-id="4b9b6-126">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-126">Select an item in the list.</span></span> <span data-ttu-id="4b9b6-127">Der Seitenbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-127">Its side pane opens.</span></span>
6. <span data-ttu-id="4b9b6-128">Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-128">In the side pane, take approve or reject actions.</span></span>

## <a name="investigation-queue"></a><span data-ttu-id="4b9b6-129">Untersuchungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="4b9b6-129">Investigation queue</span></span>

1. <span data-ttu-id="4b9b6-130">Öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-130">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-131">Navigieren Sie von der Warnungs-/Vorfallseite.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-131">Navigate from the alerts/incident page.</span></span>
3. <span data-ttu-id="4b9b6-132">Wechseln Sie auf der Seite "Untersuchung" zur Registerkarte **"Ausstehende Aktionen".**</span><span class="sxs-lookup"><span data-stu-id="4b9b6-132">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="4b9b6-133">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-133">Select an item in the list.</span></span> <span data-ttu-id="4b9b6-134">Der Seitenbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-134">Its side pane opens.</span></span>
5. <span data-ttu-id="4b9b6-135">Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-135">In the side pane, take approve or reject actions.</span></span>

## <a name="action-center"></a><span data-ttu-id="4b9b6-136">Info-Center</span><span class="sxs-lookup"><span data-stu-id="4b9b6-136">Action center</span></span>

1. <span data-ttu-id="4b9b6-137">Öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-137">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-138">Wählen Sie im Navigationsbereich **das Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-138">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="4b9b6-139">Überprüfen Sie auf der Registerkarte **"Ausstehend"** die Liste der Aktionen, die auf die Genehmigung warten.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-139">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
   - <span data-ttu-id="4b9b6-140">Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-140">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="4b9b6-141">Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-141">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="4b9b6-142">Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-142">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="investigation-and-remediation-investigations-queue"></a><span data-ttu-id="4b9b6-143">Untersuchungs- und Korrekturuntersuchungen in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="4b9b6-143">Investigation and remediation investigations queue</span></span>

1. <span data-ttu-id="4b9b6-144">Öffnen Sie das Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-144">Open the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-145">Offene Untersuchungen.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-145">Open pending investigations.</span></span>
3. <span data-ttu-id="4b9b6-146">Wechseln Sie auf der Seite "Untersuchung" zur Registerkarte **"Ausstehende Aktionen".**</span><span class="sxs-lookup"><span data-stu-id="4b9b6-146">On the Investigation page, go to the **pending actions** tab.</span></span>
4. <span data-ttu-id="4b9b6-147">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-147">Select an item in the list.</span></span> <span data-ttu-id="4b9b6-148">Der Seitenbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-148">Its side pane opens.</span></span>
5. <span data-ttu-id="4b9b6-149">Führen Sie im Seitenbereich Aktionen zum Genehmigen oder Ablehnen aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-149">In the side pane, take approve or reject actions.</span></span>

## <a name="change-or-undo-one-remediation-action"></a><span data-ttu-id="4b9b6-150">Ändern oder Rückgängigmachen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="4b9b6-150">Change or undo one remediation action</span></span>

<span data-ttu-id="4b9b6-151">Es gibt zwei verschiedene Möglichkeiten, übermittelte Aktionen zu überdenken:</span><span class="sxs-lookup"><span data-stu-id="4b9b6-151">There are two different ways to reconsider submitted actions:</span></span>

- <span data-ttu-id="4b9b6-152">Über das [einheitliche Info-Center.](https://security.microsoft.com/action-center)</span><span class="sxs-lookup"><span data-stu-id="4b9b6-152">Through the [unified action center](https://security.microsoft.com/action-center).</span></span>
- <span data-ttu-id="4b9b6-153">Obwohl das [Office Info-Center](https://security.microsoft.com/threatincidents).</span><span class="sxs-lookup"><span data-stu-id="4b9b6-153">Though the [Office action center](https://security.microsoft.com/threatincidents).</span></span>

## <a name="change-or-undo-through-the-unified-action-center"></a><span data-ttu-id="4b9b6-154">Ändern oder Rückgängigmachen über das einheitliche Info-Center</span><span class="sxs-lookup"><span data-stu-id="4b9b6-154">Change or undo through the unified action center</span></span>

1. <span data-ttu-id="4b9b6-155">Wechseln Sie zum [einheitlichen Info-Center,](https://security.microsoft.com/action-center) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-155">Go to the [unified action center](https://security.microsoft.com/action-center) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-156">Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie ändern oder rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-156">On the **History** tab, select an action that you want to change or undo.</span></span>
3. <span data-ttu-id="4b9b6-157">Wählen Sie im Bereich auf der rechten Seite des Bildschirms die entsprechende Aktion aus (**in posteingang verschieben,** **zu Junk verschieben,** zu **gelöschten Elementen verschieben,** **vorläufig löschen** oder **endgültig löschen**).</span><span class="sxs-lookup"><span data-stu-id="4b9b6-157">In the pane on the right side of the screen, select the appropriate action (**move to inbox**, **move to junk**, **move to deleted items**, **soft delete**, or **hard delete**).</span></span>

## <a name="change-or-undo-through-the-office-action-center"></a><span data-ttu-id="4b9b6-158">Ändern oder Rückgängigmachen über das Office-Info-Center</span><span class="sxs-lookup"><span data-stu-id="4b9b6-158">Change or undo through the Office action center</span></span>

1. <span data-ttu-id="4b9b6-159">Wechseln Sie zum [Info-Center Office,](https://security.microsoft.com/threatincidents) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-159">Go to the [Office action center](https://security.microsoft.com/threatincidents) and sign in.</span></span>
2. <span data-ttu-id="4b9b6-160">Wählen Sie die entsprechende Korrektur aus.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-160">Select the appropriate remediation.</span></span>
3. <span data-ttu-id="4b9b6-161">Klicken Sie im Seitenbereich auf den Eintrag für E-Mail-Übermittlungen, und warten Sie, bis die Liste geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-161">In the side pane, click on the mail submissions entry and wait for the list to load.</span></span>
4. <span data-ttu-id="4b9b6-162">Warten Sie, bis die Schaltfläche Aktion oben aktiviert ist, und wählen Sie die Schaltfläche Aktion aus, um den Aktionstyp zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-162">Wait for the Action button at the top to enable and select the Action button to change the action type.</span></span>
5. <span data-ttu-id="4b9b6-163">Dadurch werden die entsprechenden Aktionen erstellt.</span><span class="sxs-lookup"><span data-stu-id="4b9b6-163">This will create the appropriate actions.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4b9b6-164">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4b9b6-164">Next steps</span></span>

- [<span data-ttu-id="4b9b6-165">Verwenden des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="4b9b6-165">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="4b9b6-166">Administrator/Manuelle Aktionen</span><span class="sxs-lookup"><span data-stu-id="4b9b6-166">Admin /Manual Actions</span></span>](remediate-malicious-email-delivered-office-365.md)
- [<span data-ttu-id="4b9b6-167">So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="4b9b6-167">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="4b9b6-168">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="4b9b6-168">See also</span></span>

- [<span data-ttu-id="4b9b6-169">Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="4b9b6-169">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

---
title: Überprüfen und Verwalten von Korrekturaktionen in Microsoft Defender für Office 365
keywords: AIR, AutoIR, Microsoft Defender for Endpoint, automatisiert, Untersuchung, Antwort, Korrektur, Bedrohungen, erweitert, Bedrohung, Schutz
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
description: Erfahren Sie mehr über Abhilfemaßnahmen in automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender for Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: f0c42bef1b090412a7a6422fe029323b645e90df
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275072"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="72516-104">Überprüfen und Verwalten von Korrekturaktionen in Office 365</span><span class="sxs-lookup"><span data-stu-id="72516-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="72516-105">Da automatisierte Untersuchungen zu E-Mail-& Zusammenarbeitsinhalte zu  Urteilen führen, z. B. "Bösartig" oder "Verdächtig", werden bestimmte Korrekturaktionen erstellt.</span><span class="sxs-lookup"><span data-stu-id="72516-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="72516-106">In Microsoft Defender for Office 365 können Korrekturaktionen Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="72516-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="72516-107">Blockieren einer URL (Klickzeit)</span><span class="sxs-lookup"><span data-stu-id="72516-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="72516-108">Weiches Löschen von E-Mail-Nachrichten oder Clustern</span><span class="sxs-lookup"><span data-stu-id="72516-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="72516-109">Quarantining von E-Mail- oder E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="72516-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="72516-110">Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="72516-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="72516-111">Diese Korrekturaktionen werden nur dann ergriffen, wenn das Sicherheitsteam sie genehmigt hat.</span><span class="sxs-lookup"><span data-stu-id="72516-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="72516-112">Es wird empfohlen, alle ausstehenden Aktionen so schnell wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="72516-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="72516-113">In einigen Fällen können Sie eine Korrekturaktion rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="72516-113">In some cases, you can undo a remediation action.</span></span>

<span data-ttu-id="72516-114">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="72516-114">**Applies to**</span></span>
- [<span data-ttu-id="72516-115">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="72516-115">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="72516-116">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72516-116">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="72516-117">Genehmigen (oder Ablehnen) ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="72516-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="72516-118">Wechseln Sie zum Microsoft 365 Security Center ( <https://security.microsoft.com> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="72516-118">Go to the Microsoft 365 security center (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="72516-119">Wählen Sie im Navigationsbereich **Aktionscenter aus.**</span><span class="sxs-lookup"><span data-stu-id="72516-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="72516-120">Überprüfen Sie **auf der Registerkarte** Ausstehend die Liste der Aktionen, die auf die Genehmigung warten.</span><span class="sxs-lookup"><span data-stu-id="72516-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="72516-121">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="72516-121">Select an item in the list.</span></span> <span data-ttu-id="72516-122">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="72516-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="72516-123">Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="72516-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="72516-124">Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72516-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="72516-125">Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="72516-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="72516-126">Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.</span><span class="sxs-lookup"><span data-stu-id="72516-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="72516-127">Rückgängig machen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="72516-127">Undo one remediation action</span></span>

1. <span data-ttu-id="72516-128">Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="72516-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="72516-129">Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="72516-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="72516-130">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="72516-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="72516-131">Rückgängig machen mehrerer Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="72516-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="72516-132">Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="72516-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="72516-133">Wählen Sie **auf der Registerkarte** Verlauf die Aktionen aus, die Rückgängig gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="72516-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="72516-134">Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="72516-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="72516-135">Ein Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="72516-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="72516-136">Wählen Sie im Flyoutbereich Rückgängig aus.</span><span class="sxs-lookup"><span data-stu-id="72516-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="72516-137">So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="72516-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="72516-138">Wechseln Sie zum Aktionscenter ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="72516-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="72516-139">Wählen Sie **auf der Registerkarte** Verlauf eine Datei mit dem Aktionstyp **Quarantänedatei aus.**</span><span class="sxs-lookup"><span data-stu-id="72516-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="72516-140">Wählen Sie im Bereich auf der rechten Seite des Bildschirms Anwenden auf **X** weitere Instanzen dieser Datei aus, und wählen Sie **dann Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="72516-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72516-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="72516-141">Next steps</span></span>

- [<span data-ttu-id="72516-142">Verwenden des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="72516-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="72516-143">Melden falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="72516-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="72516-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72516-144">See also</span></span>

- [<span data-ttu-id="72516-145">Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="72516-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

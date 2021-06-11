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
ms.date: 01/29/2021
ms.openlocfilehash: 525f6cf922f80067219f6c33a2c11559e9e58a39
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878772"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="085e7-104">Überprüfen und Verwalten von Abhilfemaßnahmen in Office 365</span><span class="sxs-lookup"><span data-stu-id="085e7-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="085e7-105">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="085e7-105">**Applies to**</span></span>
- [<span data-ttu-id="085e7-106">Microsoft Defender für Office 365 – Plan 2</span><span class="sxs-lookup"><span data-stu-id="085e7-106">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="085e7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="085e7-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="085e7-108">Da automatisierte Untersuchungen an E-Mail-& Inhalten für die Zusammenarbeit zu Bewertungen führen, z. B. *bösartig* oder *verdächtig,* werden bestimmte Abhilfemaßnahmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="085e7-108">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="085e7-109">In Microsoft Defender für Office 365 können Korrekturaktionen Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="085e7-109">In Microsoft Defender for Office 365, remediation actions can include:</span></span>

- <span data-ttu-id="085e7-110">Blockieren einer URL (Uhrzeit des Klickens)</span><span class="sxs-lookup"><span data-stu-id="085e7-110">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="085e7-111">Vorläufiges Löschen von E-Mail-Nachrichten oder Clustern</span><span class="sxs-lookup"><span data-stu-id="085e7-111">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="085e7-112">Quarantinieren von E-Mails oder E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="085e7-112">Quarantining email or email attachments</span></span>
- <span data-ttu-id="085e7-113">Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="085e7-113">Turning off external mail forwarding</span></span>

<span data-ttu-id="085e7-114">Diese Korrekturmaßnahmen werden erst ausgeführt, wenn sie von Ihrem Sicherheitsteam genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="085e7-114">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="085e7-115">Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="085e7-115">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="085e7-116">In einigen Fällen können Sie eine Korrekturaktion rückgängigmachen.</span><span class="sxs-lookup"><span data-stu-id="085e7-116">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="085e7-117">Genehmigen (oder Ablehnen) ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="085e7-117">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="085e7-118">Wechseln Sie zum Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="085e7-118">Go to the Microsoft 365 Defender portal (<https://security.microsoft.com>) and sign in.</span></span>
2. <span data-ttu-id="085e7-119">Wählen Sie im Navigationsbereich **das Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-119">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="085e7-120">Überprüfen Sie auf der Registerkarte **"Ausstehend"** die Liste der Aktionen, die auf die Genehmigung warten.</span><span class="sxs-lookup"><span data-stu-id="085e7-120">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="085e7-121">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-121">Select an item in the list.</span></span> <span data-ttu-id="085e7-122">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="085e7-122">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="085e7-123">Überprüfen Sie die Informationen im Flyoutbereich, und führen Sie dann einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="085e7-123">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="085e7-124">Wählen Sie **die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="085e7-124">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="085e7-125">Wählen Sie **"Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="085e7-125">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="085e7-126">Wählen Sie **"Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="085e7-126">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="085e7-127">Rückgängigmachen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="085e7-127">Undo one remediation action</span></span>

1. <span data-ttu-id="085e7-128">Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="085e7-128">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="085e7-129">Wählen Sie auf der Registerkarte **"Verlauf"** eine Aktion aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="085e7-129">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="085e7-130">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig"** aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-130">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="085e7-131">Rückgängigmachen mehrerer Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="085e7-131">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="085e7-132">Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="085e7-132">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="085e7-133">Wählen Sie auf der Registerkarte **"Verlauf"** die Aktionen aus, die Sie rückgängig machen möchten.</span><span class="sxs-lookup"><span data-stu-id="085e7-133">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="085e7-134">Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="085e7-134">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="085e7-135">Ein Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="085e7-135">A flyout pane opens.</span></span>
3. <span data-ttu-id="085e7-136">Wählen Sie im Flyoutbereich "Rückgängig" aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-136">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="085e7-137">So entfernen Sie eine Datei aus der Quarantäne auf mehreren Geräten</span><span class="sxs-lookup"><span data-stu-id="085e7-137">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="085e7-138">Wechseln Sie zum Info-Center ( <https://security.microsoft.com/action-center> ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="085e7-138">Go to the Action center (<https://security.microsoft.com/action-center>) and sign in.</span></span>
2. <span data-ttu-id="085e7-139">Wählen Sie auf der Registerkarte **"Verlauf"** eine Datei mit dem Aktionstyp **"Quarantänedatei"** aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-139">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="085e7-140">Klicken Sie im Bereich auf der rechten Seite des **Bildschirms auf X weitere Instanzen dieser Datei anwenden,** und wählen Sie dann **Rückgängig** aus.</span><span class="sxs-lookup"><span data-stu-id="085e7-140">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="085e7-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="085e7-141">Next steps</span></span>

- [<span data-ttu-id="085e7-142">Verwenden des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="085e7-142">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="085e7-143">So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="085e7-143">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="085e7-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="085e7-144">See also</span></span>

- [<span data-ttu-id="085e7-145">Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="085e7-145">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

---
title: Überprüfen und Verwalten von Wartungsaktionen in Microsoft Defender für Office 365
keywords: AIR, AutoIR, ATP, automatisiert, Untersuchung, Reaktion, Problembehebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Erfahren Sie mehr über Abhilfemaßnahmen bei automatisierten Untersuchungs- und Reaktionsfunktionen in Microsoft Defender für Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: bcff8f12133ea16e3d91e293943be1593eaf9659
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142693"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a><span data-ttu-id="c45a8-104">Überprüfen und Verwalten von Wartungsaktionen in Office 365</span><span class="sxs-lookup"><span data-stu-id="c45a8-104">Review and manage remediation actions in Office 365</span></span>

<span data-ttu-id="c45a8-105">Da automatisierte Untersuchungen von E-mail-& zusammenarbeitsinhalten  zu Bekündungen führen, z. B. bösartig oder verdächtig, werden bestimmte Abhilfemaßnahmen erstellt.</span><span class="sxs-lookup"><span data-stu-id="c45a8-105">As automated investigations on email & collaboration content result in verdicts, such as *Malicious* or *Suspicious*, certain remediation actions are created.</span></span> <span data-ttu-id="c45a8-106">In Microsoft Defender für Office 365 können Wiederherstellungsaktionen Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="c45a8-106">In Microsoft Defender for Office 365, remediation actions can include:</span></span>
- <span data-ttu-id="c45a8-107">Blockieren einer URL (Zeitpunkt des Klicks)</span><span class="sxs-lookup"><span data-stu-id="c45a8-107">Blocking a URL (time-of-click)</span></span>
- <span data-ttu-id="c45a8-108">Soft deleting email messages or clusters</span><span class="sxs-lookup"><span data-stu-id="c45a8-108">Soft deleting email messages or clusters</span></span>
- <span data-ttu-id="c45a8-109">Quarantining von E-Mail- oder E-Mail-Anlagen</span><span class="sxs-lookup"><span data-stu-id="c45a8-109">Quarantining email or email attachments</span></span>
- <span data-ttu-id="c45a8-110">Deaktivieren der externen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="c45a8-110">Turning off external mail forwarding</span></span>

<span data-ttu-id="c45a8-111">Diese Abhilfemaßnahmen werden erst dann ergriffen, wenn sie vom Sicherheitsteam genehmigt werden.</span><span class="sxs-lookup"><span data-stu-id="c45a8-111">These remediation actions are not taken unless and until your security operations team approves them.</span></span> <span data-ttu-id="c45a8-112">Es wird empfohlen, alle ausstehenden Aktionen so bald wie möglich zu überprüfen und zu genehmigen, damit Ihre automatisierten Untersuchungen zeitnah abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="c45a8-112">We recommend reviewing and approving any pending actions as soon as possible so that your automated investigations complete in a timely manner.</span></span> <span data-ttu-id="c45a8-113">In einigen Fällen können Sie eine Korrekturaktion rückgängig machen.</span><span class="sxs-lookup"><span data-stu-id="c45a8-113">In some cases, you can undo a remediation action.</span></span>

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="c45a8-114">Genehmigen (oder Ablehnen) ausstehender Aktionen</span><span class="sxs-lookup"><span data-stu-id="c45a8-114">Approve (or reject) pending actions</span></span>

1. <span data-ttu-id="c45a8-115">Wechseln Sie zum Microsoft 365 Security [https://security.microsoft.com](https://security.microsoft.com) Center, und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c45a8-115">Go to the Microsoft 365 security center [https://security.microsoft.com](https://security.microsoft.com)) and sign in.</span></span>
2. <span data-ttu-id="c45a8-116">Wählen Sie im Navigationsbereich **"Aktionscenter" aus.**</span><span class="sxs-lookup"><span data-stu-id="c45a8-116">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="c45a8-117">Überprüfen Sie **auf der Registerkarte** "Ausstehend" die Liste der Aktionen, die auf eine Genehmigung warten.</span><span class="sxs-lookup"><span data-stu-id="c45a8-117">On the **Pending** tab, review the list of actions that are awaiting approval.</span></span>
4. <span data-ttu-id="c45a8-118">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="c45a8-118">Select an item in the list.</span></span> <span data-ttu-id="c45a8-119">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c45a8-119">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="c45a8-120">Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c45a8-120">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="c45a8-121">Wählen **Sie die Seite "Untersuchung öffnen"** aus, um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c45a8-121">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="c45a8-122">Wählen **Sie "Genehmigen"** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="c45a8-122">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="c45a8-123">Wählen **Sie "Ablehnen"** aus, um zu verhindern, dass eine ausstehende Aktion abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c45a8-123">Select **Reject** to prevent a pending action from being taken.</span></span>

## <a name="undo-one-remediation-action"></a><span data-ttu-id="c45a8-124">Rückgängig machen einer Wartungsaktion</span><span class="sxs-lookup"><span data-stu-id="c45a8-124">Undo one remediation action</span></span>

1. <span data-ttu-id="c45a8-125">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c45a8-125">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="c45a8-126">Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="c45a8-126">On the **History** tab, select an action that you want to undo.</span></span>
3. <span data-ttu-id="c45a8-127">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig" aus.**</span><span class="sxs-lookup"><span data-stu-id="c45a8-127">In the pane on the right side of the screen, select **Undo**.</span></span>

## <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="c45a8-128">Rückgängig machen mehrerer Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="c45a8-128">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="c45a8-129">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c45a8-129">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="c45a8-130">Wählen Sie **auf der** Registerkarte "Verlauf" die Aktionen aus, die Rückgängig gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c45a8-130">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="c45a8-131">Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="c45a8-131">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="c45a8-132">Ein Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c45a8-132">A flyout pane opens.</span></span>
3. <span data-ttu-id="c45a8-133">Wählen Sie im Flyoutbereich "Rückgängig" aus.</span><span class="sxs-lookup"><span data-stu-id="c45a8-133">In the flyout pane, select Undo.</span></span>

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="c45a8-134">So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="c45a8-134">To remove a file from quarantine across multiple devices</span></span>

1. <span data-ttu-id="c45a8-135">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="c45a8-135">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>
2. <span data-ttu-id="c45a8-136">Wählen Sie **auf der Registerkarte** "Verlauf" eine Datei mit dem Aktionstyp **"Quarantäne" aus.**</span><span class="sxs-lookup"><span data-stu-id="c45a8-136">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>
3. <span data-ttu-id="c45a8-137">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Auf X** weitere Instanzen dieser Datei anwenden" und dann **"Rückgängig" aus.**</span><span class="sxs-lookup"><span data-stu-id="c45a8-137">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c45a8-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c45a8-138">Next steps</span></span>

- [<span data-ttu-id="c45a8-139">Verwenden des Bedrohungs-Explorers</span><span class="sxs-lookup"><span data-stu-id="c45a8-139">Use Threat Explorer</span></span>](threat-explorer.md)
- [<span data-ttu-id="c45a8-140">So melden Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="c45a8-140">How to report false positives/negatives in automated investigation and response capabilities</span></span>](air-report-false-positives-negatives.md)

## <a name="see-also"></a><span data-ttu-id="c45a8-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c45a8-141">See also</span></span>

- [<span data-ttu-id="c45a8-142">Anzeigen von Details und Ergebnissen einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="c45a8-142">View details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

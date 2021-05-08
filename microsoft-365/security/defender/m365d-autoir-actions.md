---
title: Anzeigen und Verwalten von Aktionen im Aktionscenter
description: Anzeigen und Verwalten von Korrekturaktionen mithilfe des Aktionscenters
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
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
ms.openlocfilehash: e3e842f812c5675334cc25fa35544165129db2b4
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245888"
---
# <a name="view-and-manage-actions-in-the-action-center"></a><span data-ttu-id="51307-104">Anzeigen und Verwalten von Aktionen im Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="51307-104">View and manage actions in the Action center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="51307-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51307-105">**Applies to:**</span></span>
- <span data-ttu-id="51307-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51307-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="51307-107">Bedrohungsschutzfeatures in Microsoft 365 Defender können zu bestimmten Korrekturaktionen führen.</span><span class="sxs-lookup"><span data-stu-id="51307-107">Threat protection features in Microsoft 365 Defender can result in certain remediation actions.</span></span> <span data-ttu-id="51307-108">Im Folgenden finden Sie einige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="51307-108">Here are some examples:</span></span>
- <span data-ttu-id="51307-109">[Automatisierte Untersuchungen](m365d-autoir.md) können zu Korrekturaktionen führen, die automatisch ausgeführt werden oder auf die Genehmigung warten.</span><span class="sxs-lookup"><span data-stu-id="51307-109">[Automated investigations](m365d-autoir.md) can result in remediation actions that are taken automatically or await approval.</span></span>
- <span data-ttu-id="51307-110">Antivirus-, Antischamalware- und andere Bedrohungsschutzfeatures können zu Abhilfemaßnahmen führen, z. B. das Blockieren einer Datei, URL oder eines Prozesses oder das Senden eines Artefakts in Quarantäne.</span><span class="sxs-lookup"><span data-stu-id="51307-110">Antivirus, antimalware, and other threat protection features can result in remediation actions, such as blocking a file, URL, or process, or sending an artifact to quarantine.</span></span>
- <span data-ttu-id="51307-111">Ihr Sicherheitsteam kann Korrekturaktionen manuell ausführen, [](advanced-hunting-overview.md) z. B. während der erweiterten Suche oder bei der Untersuchung von [Warnungen](investigate-alerts.md) oder [Vorfällen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="51307-111">Your security operations team can take remediation actions manually, such as during [advanced hunting](advanced-hunting-overview.md) or while investigating [alerts](investigate-alerts.md) or [incidents](investigate-incidents.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51307-112">Sie müssen über [geeignete Berechtigungen verfügen](m365d-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können.</span><span class="sxs-lookup"><span data-stu-id="51307-112">You must have [appropriate permissions](m365d-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="51307-113">Weitere Informationen finden Sie unter [Voraussetzungen für die automatisierte Untersuchung und](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)Reaktion in Microsoft 365 Defender .</span><span class="sxs-lookup"><span data-stu-id="51307-113">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](m365d-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-pending-actions-in-the-action-center"></a><span data-ttu-id="51307-114">Überprüfen ausstehender Aktionen im Aktionscenter</span><span class="sxs-lookup"><span data-stu-id="51307-114">Review pending actions in the Action center</span></span>

<span data-ttu-id="51307-115">Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="51307-115">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)

1. <span data-ttu-id="51307-117">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="51307-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="51307-118">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="51307-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="51307-119">Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="51307-119">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> <span data-ttu-id="51307-120">Der Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51307-120">Its flyout pane opens.</span></span>

4. <span data-ttu-id="51307-121">Überprüfen Sie die Informationen im Flyoutbereich, und gehen Sie dann wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="51307-121">Review the information in the flyout pane, and then take one of the following steps:</span></span>
   - <span data-ttu-id="51307-122">Wählen **Sie Die Seite Untersuchung öffnen aus,** um weitere Details zur Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="51307-122">Select **Open investigation page** to view more details about the investigation.</span></span>
   - <span data-ttu-id="51307-123">Wählen **Sie Genehmigen** aus, um eine ausstehende Aktion zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="51307-123">Select **Approve** to initiate a pending action.</span></span>
   - <span data-ttu-id="51307-124">Wählen **Sie Ablehnen** aus, um zu verhindern, dass eine ausstehende Aktion ergriffen wird.</span><span class="sxs-lookup"><span data-stu-id="51307-124">Select **Reject** to prevent a pending action from being taken.</span></span>
   - <span data-ttu-id="51307-125">Wählen **Sie Auf Die Suche gehen** aus, um zu Erweiterte Suche zu [wechseln.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="51307-125">Select **Go hunt** to go into [Advanced hunting](advanced-hunting-overview.md).</span></span> 

## <a name="undo-completed-actions"></a><span data-ttu-id="51307-126">Rückgängig machen abgeschlossener Aktionen</span><span class="sxs-lookup"><span data-stu-id="51307-126">Undo completed actions</span></span>

<span data-ttu-id="51307-127">Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung darstellt, können Sie die ergriffenen Korrekturaktionen rückgängig machen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="51307-127">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="51307-128">Im Aktionscenter können Sie auf der Registerkarte **Verlauf** eine der folgenden Aktionen rückgängig machen:</span><span class="sxs-lookup"><span data-stu-id="51307-128">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="51307-129">Aktionsquelle</span><span class="sxs-lookup"><span data-stu-id="51307-129">Action source</span></span> | <span data-ttu-id="51307-130">Unterstützte Aktionen</span><span class="sxs-lookup"><span data-stu-id="51307-130">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="51307-131">– Automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="51307-131">- Automated investigation</span></span> <br/><span data-ttu-id="51307-132">- Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="51307-132">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="51307-133">– Manuelle Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="51307-133">- Manual response actions</span></span> | <span data-ttu-id="51307-134">- Gerät isolieren</span><span class="sxs-lookup"><span data-stu-id="51307-134">- Isolate device</span></span> <br/><span data-ttu-id="51307-135">- Einschränken der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="51307-135">- Restrict code execution</span></span> <br/><span data-ttu-id="51307-136">– Isolieren einer Datei</span><span class="sxs-lookup"><span data-stu-id="51307-136">- Quarantine a file</span></span> <br/><span data-ttu-id="51307-137">- Entfernen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="51307-137">- Remove a registry key</span></span> <br/><span data-ttu-id="51307-138">- Beenden eines Diensts</span><span class="sxs-lookup"><span data-stu-id="51307-138">- Stop a service</span></span> <br/><span data-ttu-id="51307-139">- Deaktivieren eines Treibers</span><span class="sxs-lookup"><span data-stu-id="51307-139">- Disable a driver</span></span> <br/><span data-ttu-id="51307-140">– Entfernen eines geplanten Vorgangs</span><span class="sxs-lookup"><span data-stu-id="51307-140">- Remove a scheduled task</span></span> |

### <a name="undo-one-remediation-action"></a><span data-ttu-id="51307-141">Rückgängig machen einer Korrekturaktion</span><span class="sxs-lookup"><span data-stu-id="51307-141">Undo one remediation action</span></span>

1. <span data-ttu-id="51307-142">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="51307-142">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="51307-143">Wählen Sie **auf der** Registerkarte Verlauf eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="51307-143">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="51307-144">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="51307-144">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="undo-multiple-remediation-actions"></a><span data-ttu-id="51307-145">Rückgängig machen mehrerer Korrekturaktionen</span><span class="sxs-lookup"><span data-stu-id="51307-145">Undo multiple remediation actions</span></span>

1. <span data-ttu-id="51307-146">Wechseln Sie zum Aktionscenter ( https://security.microsoft.com/action-center) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="51307-146">Go to the Action center (https://security.microsoft.com/action-center) and sign in.</span></span>

2. <span data-ttu-id="51307-147">Wählen Sie **auf der Registerkarte** Verlauf die Aktionen aus, die Rückgängig gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="51307-147">On the **History** tab, select the actions that you want to undo.</span></span> <span data-ttu-id="51307-148">Stellen Sie sicher, dass Sie Elemente mit demselben Aktionstyp auswählen.</span><span class="sxs-lookup"><span data-stu-id="51307-148">Make sure to select items that have the same Action type.</span></span> <span data-ttu-id="51307-149">Ein Flyoutbereich wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="51307-149">A flyout pane opens.</span></span>

3. <span data-ttu-id="51307-150">Wählen Sie im Flyoutbereich **Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="51307-150">In the flyout pane, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="51307-151">So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="51307-151">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="51307-152">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="51307-152">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="51307-153">Wählen Sie **auf der Registerkarte** Verlauf eine Datei mit dem Aktionstyp **Quarantänedatei aus.**</span><span class="sxs-lookup"><span data-stu-id="51307-153">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="51307-154">Wählen Sie im Bereich auf der rechten Seite des Bildschirms Anwenden auf **X** weitere Instanzen dieser Datei aus, und wählen Sie **dann Rückgängig aus.**</span><span class="sxs-lookup"><span data-stu-id="51307-154">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="51307-155">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="51307-155">Next steps</span></span>

- [<span data-ttu-id="51307-156">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="51307-156">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="51307-157">Erfahren Sie, wie Sie falsch positive/negative Ergebnisse behandeln (wenn Sie eins erhalten)</span><span class="sxs-lookup"><span data-stu-id="51307-157">Learn how to handle false positives/negatives (if you get one)</span></span>](m365d-autoir-report-false-positives-negatives.md)

---
title: Genehmigen oder Ablehnen ausstehender Aktionen nach einer automatischen Untersuchung
description: Verwenden des Info-Centers zum Verwalten von Aktionen im Zusammenhang mit automatisierten Untersuchungen und Reaktionen
keywords: Aktion, Center, autoair, automatisiert, Untersuchung, Reaktion, Problembehebung
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930378"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a><span data-ttu-id="67900-104">Genehmigen oder Ablehnen ausstehender Aktionen nach einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="67900-104">Approve or reject pending actions following an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="67900-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="67900-105">**Applies to:**</span></span>
- <span data-ttu-id="67900-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67900-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="67900-107">Wenn eine automatisierte Untersuchung ausgeführt wird, kann dies zu einer oder mehreren empfohlenen [Abhilfemaßnahmen](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) führen, für die eine Genehmigung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="67900-107">When an automated investigation runs, it can result in one or more [remediation actions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) that require approval to proceed.</span></span> <span data-ttu-id="67900-108">So kann beispielsweise ein Cluster von E-Mail-Nachrichten gelöscht oder eine in Quarantäne befindliche Datei entfernt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="67900-108">For example, a cluster of email messages might need to be deleted, or a quarantined file might need to be removed.</span></span> <span data-ttu-id="67900-109">Es ist wichtig, ausstehende Aktionen so bald wie möglich zu genehmigen (oder abzulehnen), damit Ihre automatisierten Untersuchungen zeitnah fortgesetzt und abgeschlossen werden können.</span><span class="sxs-lookup"><span data-stu-id="67900-109">It's important to approve (or reject) pending actions as soon as possible so that your automated investigations can proceed and complete in a timely manner.</span></span> 

> [!TIP]
> <span data-ttu-id="67900-110">Wenn Sie denken, dass etwas von automatisierten Untersuchungs- und Antwortfeatures in Microsoft 365 Defender übersehen oder falsch erkannt wurde, lassen Sie es uns wissen!</span><span class="sxs-lookup"><span data-stu-id="67900-110">If you think something was missed or wrongly detected by automated investigation and response features in Microsoft 365 Defender, let us know!</span></span> <span data-ttu-id="67900-111">Erfahren [Sie, wie Sie falsch positive/negative Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen (AIR) in Microsoft 365 Defender melden.](mtp-autoir-report-false-positives-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="67900-111">See [How to report false positives/negatives in automated investigation and response (AIR) capabilities in Microsoft 365 Defender](mtp-autoir-report-false-positives-negatives.md).</span></span>

<span data-ttu-id="67900-112">Ausstehende Aktionen können mithilfe des [](#review-a-pending-action-in-the-action-center) Aktionscenters oder der Ansicht "Untersuchungsdetails" überprüft [und genehmigt werden.](#review-a-pending-action-in-the-investigation-details-view)</span><span class="sxs-lookup"><span data-stu-id="67900-112">Pending actions can be reviewed and approved by using the [Action center](#review-a-pending-action-in-the-action-center) or the [investigation details view](#review-a-pending-action-in-the-investigation-details-view).</span></span>

> [!NOTE]
> <span data-ttu-id="67900-113">Sie müssen über [geeignete Berechtigungen verfügen](mtp-action-center.md#required-permissions-for-action-center-tasks), um Abhilfemaßnahmen genehmigen oder ablehnen zu können.</span><span class="sxs-lookup"><span data-stu-id="67900-113">You must have [appropriate permissions](mtp-action-center.md#required-permissions-for-action-center-tasks) to approve or reject remediation actions.</span></span> <span data-ttu-id="67900-114">Weitere Informationen finden Sie unter [Voraussetzungen für die automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="67900-114">For more information, see [Prerequisites for automated investigation and response in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender).</span></span>

## <a name="review-a-pending-action-in-the-action-center"></a><span data-ttu-id="67900-115">Überprüfen einer ausstehenden Aktion im Info-Center</span><span class="sxs-lookup"><span data-stu-id="67900-115">Review a pending action in the Action center</span></span>

1. <span data-ttu-id="67900-116">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="67900-116">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="67900-117">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="67900-117">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="67900-118">Wählen Sie im Info-Center auf der Registerkarte **Ausstehend** ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="67900-118">In the Action Center, on the **Pending** tab, select an item in the list.</span></span> 

    - <span data-ttu-id="67900-119">Wenn Sie ein Element in der Spalte **Nummer der Untersuchung** auswählen, wird die Seite mit den Untersuchungsdetails geöffnet.</span><span class="sxs-lookup"><span data-stu-id="67900-119">If you select an item in the **Investigation number** column, the investigation details page opens.</span></span> <span data-ttu-id="67900-120">Dort können Sie die Ergebnisse der Untersuchung anzeigen und dann die empfohlenen Aktionen genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="67900-120">There, you can view the results of the investigation, and then either approve or reject the recommended action.</span></span>
 
    - <span data-ttu-id="67900-121">Wenn Sie eine Zeile in der Liste auswählen, wird ein Flyout geöffnet, in dem Informationen zu dem betreffenden Element angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="67900-121">If you select a row in the list, a flyout opens, where you can view information about that item.</span></span> <br/>![Genehmigen oder Ablehnen einer Aktion](../../media/air-actioncenter-itemselected.png)<br/><span data-ttu-id="67900-123">Verwenden Sie die Links, um eine zugeordnete Warnung oder eine Untersuchung anzuzeigen, und genehmigen Sie die jeweilige Aktion oder lehnen Sie diese ab.</span><span class="sxs-lookup"><span data-stu-id="67900-123">Use the links to view an associated alert or an investigation, and approve or reject the action.</span></span>

## <a name="review-a-pending-action-in-the-investigation-details-view"></a><span data-ttu-id="67900-124">Überprüfen einer ausstehenden Aktion in der Untersuchungsdetailansicht</span><span class="sxs-lookup"><span data-stu-id="67900-124">Review a pending action in the investigation details view</span></span>

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

1. <span data-ttu-id="67900-126">Wählen Sie auf der Seite [Untersuchungsdetails](mtp-autoir-results.md) die Option **Ausstehende Aktionen** (oder **Aktionen**) aus. Hier sind die Elemente aufgelistet, für die eine Genehmigung aussteht.</span><span class="sxs-lookup"><span data-stu-id="67900-126">On an [investigation details](mtp-autoir-results.md) page, select the **Pending actions** (or **Actions**) tab. Items that are pending approval are listed here.</span></span>

2. <span data-ttu-id="67900-127">Wählen Sie ein Element in der Liste aus, und wählen Sie dann **Genehmigen** oder **Ablehnen** aus.</span><span class="sxs-lookup"><span data-stu-id="67900-127">Select an item in the list, and then choose **Approve** or **Reject**.</span></span>

## <a name="undo-completed-actions"></a><span data-ttu-id="67900-128">Abgeschlossene Aktionen rückgängig machen</span><span class="sxs-lookup"><span data-stu-id="67900-128">Undo completed actions</span></span>

<span data-ttu-id="67900-129">Wenn Sie festgestellt haben, dass ein Gerät oder eine Datei keine Bedrohung darstellt, können Sie die ergriffenen Abhilfemaßnahmen rückgängig machen, unabhängig davon, ob diese Aktionen automatisch oder manuell ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="67900-129">If you’ve determined that a device or a file is not a threat, you can undo remediation actions that were taken, whether those actions were taken automatically or manually.</span></span> <span data-ttu-id="67900-130">Im Aktionscenter können Sie auf **der** Registerkarte "Verlauf" eine der folgenden Aktionen rückgängig machen:</span><span class="sxs-lookup"><span data-stu-id="67900-130">In the Action center, on the **History** tab, you can undo any of the following actions:</span></span>  

| <span data-ttu-id="67900-131">Aktionsquelle</span><span class="sxs-lookup"><span data-stu-id="67900-131">Action source</span></span> | <span data-ttu-id="67900-132">Unterstützte Aktionen</span><span class="sxs-lookup"><span data-stu-id="67900-132">Supported Actions</span></span> |
|:---|:---|
| <span data-ttu-id="67900-133">– Automatisierte Untersuchung</span><span class="sxs-lookup"><span data-stu-id="67900-133">- Automated investigation</span></span> <br/><span data-ttu-id="67900-134">– Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="67900-134">- Microsoft Defender Antivirus</span></span> <br/><span data-ttu-id="67900-135">– Manuelle Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="67900-135">- Manual response actions</span></span> | <span data-ttu-id="67900-136">- Gerät isolieren</span><span class="sxs-lookup"><span data-stu-id="67900-136">- Isolate device</span></span> <br/><span data-ttu-id="67900-137">– Einschränken der Codeausführung</span><span class="sxs-lookup"><span data-stu-id="67900-137">- Restrict code execution</span></span> <br/><span data-ttu-id="67900-138">– Isolieren einer Datei</span><span class="sxs-lookup"><span data-stu-id="67900-138">- Quarantine a file</span></span> <br/><span data-ttu-id="67900-139">– Entfernen eines Registrierungsschlüssels</span><span class="sxs-lookup"><span data-stu-id="67900-139">- Remove a registry key</span></span> <br/><span data-ttu-id="67900-140">– Beenden eines Diensts</span><span class="sxs-lookup"><span data-stu-id="67900-140">- Stop a service</span></span> <br/><span data-ttu-id="67900-141">– Deaktivieren eines Treibers</span><span class="sxs-lookup"><span data-stu-id="67900-141">- Disable a driver</span></span> <br/><span data-ttu-id="67900-142">– Entfernen eines geplanten Vorgangs</span><span class="sxs-lookup"><span data-stu-id="67900-142">- Remove a scheduled task</span></span> |

### <a name="to-undo-a-remediation-action"></a><span data-ttu-id="67900-143">So machen Sie eine Wartungsaktion rückgängig</span><span class="sxs-lookup"><span data-stu-id="67900-143">To undo a remediation action</span></span>

1. <span data-ttu-id="67900-144">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="67900-144">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="67900-145">Wählen Sie **auf der** Registerkarte "Verlauf" eine Aktion aus, die Rückgängig gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="67900-145">On the **History** tab, select an action that you want to undo.</span></span>

3. <span data-ttu-id="67900-146">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Rückgängig" aus.**</span><span class="sxs-lookup"><span data-stu-id="67900-146">In the pane on the right side of the screen, select **Undo**.</span></span>

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a><span data-ttu-id="67900-147">So entfernen Sie eine Datei auf mehreren Geräten aus der Quarantäne</span><span class="sxs-lookup"><span data-stu-id="67900-147">To remove a file from quarantine across multiple devices</span></span> 

1. <span data-ttu-id="67900-148">Wechseln Sie zum Aktionscenter ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="67900-148">Go to the Action center ([https://security.microsoft.com/action-center](https://security.microsoft.com/action-center)) and sign in.</span></span>

2. <span data-ttu-id="67900-149">Wählen Sie **auf der Registerkarte** "Verlauf" eine Datei mit dem Aktionstyp **"Quarantäne" aus.**</span><span class="sxs-lookup"><span data-stu-id="67900-149">On the **History** tab, select a file that has the Action type **Quarantine file**.</span></span>

3. <span data-ttu-id="67900-150">Wählen Sie im Bereich auf der rechten Seite des Bildschirms **"Auf X** weitere Instanzen dieser Datei anwenden" und dann **"Rückgängig" aus.**</span><span class="sxs-lookup"><span data-stu-id="67900-150">In the pane on the right side of the screen, select **Apply to X more instances of this file**, and then select **Undo**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="67900-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="67900-151">Next steps</span></span>

- [<span data-ttu-id="67900-152">Anzeigen der Details und Ergebnisse einer automatischen Untersuchung</span><span class="sxs-lookup"><span data-stu-id="67900-152">View the details and results of an automated investigation</span></span>](mtp-autoir-results.md)
- [<span data-ttu-id="67900-153">Behandeln falsch positiver/negativer Ergebnisse in automatisierten Untersuchungs- und Reaktionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="67900-153">Handle false positives/negatives in automated investigation and response capabilities</span></span>](mtp-autoir-report-false-positives-negatives.md)

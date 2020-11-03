---
title: Details und Ergebnisse einer automatisierten Untersuchung
description: Während und nach einer automatischen Untersuchung können Sie die Ergebnisse und die wichtigsten Erkenntnisse anzeigen.
keywords: automatisch, Untersuchungen, Ergebnisse, analysieren, Details, Behebung, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.date: 09/16/2020
ms.openlocfilehash: 183435596706855479c49abc34358c85dccb0da4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846508"
---
# <a name="details-and-results-of-an-automated-investigation"></a><span data-ttu-id="8bb43-104">Details und Ergebnisse einer automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="8bb43-104">Details and results of an automated investigation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8bb43-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8bb43-105">**Applies to:**</span></span>
- <span data-ttu-id="8bb43-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8bb43-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="8bb43-107">Wenn in Microsoft 365 Defender eine automatisierte Untersuchung erfolgt, sind Details zu dieser Untersuchung während und nach dem automatisierten Ermittlungsprozess verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8bb43-107">When an automated investigation occurs in Microsoft 365 Defender, details about that investigation are available during and after the automated investigation process.</span></span> <span data-ttu-id="8bb43-108">Wenn Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie diese Details in einer unter Anzeige mit Untersuchungsdetails anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-108">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can view those details in an investigation details view.</span></span> <span data-ttu-id="8bb43-109">Die Anzeige mit Untersuchungsdetails bieten Ihnen den aktuellen Status sowie die Möglichkeit, ausstehende Aktionen zu genehmigen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-109">The investigation details view provides you with up-to-date status and the ability to approve any pending actions.</span></span> 

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a><span data-ttu-id="8bb43-111">Öffnen der Anzeige mit Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="8bb43-111">Open the investigation details view</span></span>

<span data-ttu-id="8bb43-112">Mit einer der folgenden Methoden können Sie die Anzeige mit Untersuchungsdetails öffnen:</span><span class="sxs-lookup"><span data-stu-id="8bb43-112">You can open the investigation details view by using one of the following methods:</span></span>
- [<span data-ttu-id="8bb43-113">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="8bb43-113">Select an item in the Action center</span></span>](#select-an-item-in-the-action-center)
- [<span data-ttu-id="8bb43-114">Auswählen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="8bb43-114">Select an investigation from an incident details page</span></span>](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a><span data-ttu-id="8bb43-115">Auswählen eines Elements im Info-Center</span><span class="sxs-lookup"><span data-stu-id="8bb43-115">Select an item in the Action center</span></span>

<span data-ttu-id="8bb43-116">Verwenden Sie das Info-Center, um Aktionen anzuzeigen, deren Genehmigung aussteht (auf der Registerkarte **Ausstehend** ) oder die bereits genehmigt wurden (auf der Registerkarte **Verlauf** ).</span><span class="sxs-lookup"><span data-stu-id="8bb43-116">Use the Action center to view actions that are either pending approval (on the **Pending** tab) or were already approved (on the **History** tab).</span></span> 

1. <span data-ttu-id="8bb43-117">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="8bb43-117">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8bb43-118">Wählen Sie im Navigationsbereich **Info-Center** aus.</span><span class="sxs-lookup"><span data-stu-id="8bb43-118">In the navigation pane, choose **Action center**.</span></span> 

3. <span data-ttu-id="8bb43-119">Wählen Sie auf der Registerkarte **Ausstehend** oder **Verlauf** ein Element aus.</span><span class="sxs-lookup"><span data-stu-id="8bb43-119">On either the **Pending** or **History** tab, select an item.</span></span> <span data-ttu-id="8bb43-120">Wenn Sie über die [erforderlichen Berechtigungen](mtp-action-center.md#required-permissions-for-action-center-tasks) verfügen, können Sie ausstehende Aktionen genehmigen (oder ablehnen).</span><span class="sxs-lookup"><span data-stu-id="8bb43-120">If you have the [necessary permissions](mtp-action-center.md#required-permissions-for-action-center-tasks), you can approve (or reject) pending actions.</span></span>

### <a name="open-an-investigation-from-an-incident-details-page"></a><span data-ttu-id="8bb43-121">Öffnen einer Untersuchung von einer Vorfalldetailsseite</span><span class="sxs-lookup"><span data-stu-id="8bb43-121">Open an investigation from an incident details page</span></span>

<span data-ttu-id="8bb43-122">Verwenden Sie die Seite „Vorfalldetails“, um detaillierte Informationen zu einem Vorfall anzuzeigen, einschließlich ausgelöster Warnungen und Informationen zu betroffenen Geräten, Benutzerkonten oder Postfächern.</span><span class="sxs-lookup"><span data-stu-id="8bb43-122">Use an incident details page to view detailed information about an incident, including alerts that were triggered information about any affected devices, user accounts, or mailboxes.</span></span>

1. <span data-ttu-id="8bb43-123">Gehen Sie zu [https://security.microsoft.com](https://security.microsoft.com), und melden Sie sich an.</span><span class="sxs-lookup"><span data-stu-id="8bb43-123">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 

2. <span data-ttu-id="8bb43-124">Wählen Sie im Navigationsbereich **Vorfälle** aus.</span><span class="sxs-lookup"><span data-stu-id="8bb43-124">In the navigation pane, choose **Incidents**.</span></span> 

3. <span data-ttu-id="8bb43-125">Wählen Sie ein Element in der Liste aus, um die Vorfalldetailsseite zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-125">Select an item in the list to open the incident details view.</span></span><br/>![Vorfalldetails](../../media/mtp-incidentdetails-tabs.png)

4. <span data-ttu-id="8bb43-127">Wählen Sie auf der Registerkarte **Untersuchung** eine Untersuchung in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="8bb43-127">On the **Investigations** tab, select an investigation in the list.</span></span>

## <a name="investigation-details"></a><span data-ttu-id="8bb43-128">Untersuchungsdetails</span><span class="sxs-lookup"><span data-stu-id="8bb43-128">Investigation details</span></span>

<span data-ttu-id="8bb43-129">Verwenden Sie die Anzeige mit Untersuchungsdetails, um vergangene, aktuelle und ausstehende Aktivitäten im Zusammenhang mit einer Untersuchung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-129">Use the investigation details view to see past, current, and pending activity pertaining to an investigation.</span></span> <span data-ttu-id="8bb43-130">Die Anzeige mit Untersuchungsdetails sieht wie in der folgenden Abbildung aus:</span><span class="sxs-lookup"><span data-stu-id="8bb43-130">The investigation details view resembles the following image:</span></span>

![Untersuchungsdetails](../../media/mtp-air-investdetails.png)

<span data-ttu-id="8bb43-132">In der Anzeige mit Untersuchungsdetails können Sie Informationen im **Untersuchungsdiagramm** sowie auf den Registerkarten **Benachrichtigungen** , **Geräte** , **Identitäten** , **Wichtige Erkenntnisse** , **Entitäten** , **Protokoll** und **Ausstehende Aktionen** anzeigen, die in der folgenden Tabelle beschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="8bb43-132">In the Investigation details view, you can see information on the **Investigation graph** , **Alerts** , **Devices** , **Identities** , **Key findings** , **Entities** , **Log** , and **Pending actions** tabs, described in the following table.</span></span>

|<span data-ttu-id="8bb43-133">Registerkarte</span><span class="sxs-lookup"><span data-stu-id="8bb43-133">Tab</span></span>    |<span data-ttu-id="8bb43-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8bb43-134">Description</span></span> |
|--------|--------|
|<span data-ttu-id="8bb43-135">Untersuchungsdiagramm</span><span class="sxs-lookup"><span data-stu-id="8bb43-135">Investigation graph</span></span>    |<span data-ttu-id="8bb43-136">Bietet eine visuelle Darstellung der Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="8bb43-136">Provides a visual representation of the investigation.</span></span> <span data-ttu-id="8bb43-137">Stellt Entitäten dar und listet gefundene Bedrohungen zusammen mit Warnungen und Informationen dazu auf, ob Aktionen genehmigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-137">Depicts entities and lists threats found, along with alerts and whether any actions are awaiting approval.</span></span><br/><span data-ttu-id="8bb43-138">Sie können auf ein Element im Diagramm klicken, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-138">You can click an item on the graph to view more details.</span></span> <span data-ttu-id="8bb43-139">Wenn Sie beispielsweise auf das Symbol **Bedrohungen gefunden** klicken, gelangen Sie zur Registerkarte **Wichtige Erkenntnisse**.</span><span class="sxs-lookup"><span data-stu-id="8bb43-139">For example, clicking the **Threats found** icon takes you to the **Key findings** tab.</span></span> |
|<span data-ttu-id="8bb43-140">Warnungen</span><span class="sxs-lookup"><span data-stu-id="8bb43-140">Alerts</span></span> |<span data-ttu-id="8bb43-141">Listet die mit der Untersuchung verbundenen Warnungen auf.</span><span class="sxs-lookup"><span data-stu-id="8bb43-141">Lists alerts associated with the investigation.</span></span> <span data-ttu-id="8bb43-142">Warnungen können aus den Features zum Schutz vor Bedrohungen auf dem Computer eines Benutzers, aus Office-Apps, aus Cloud App Security und aus anderen Features von Microsoft 365 Threat Protection stammen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-142">Alerts can come from threat protection features on a user's machine, in Office apps, Cloud App Security, and other Microsoft 365 Threat Protection features.</span></span>|
|<span data-ttu-id="8bb43-143">Geräte</span><span class="sxs-lookup"><span data-stu-id="8bb43-143">Devices</span></span>|<span data-ttu-id="8bb43-144">Listet die in die Untersuchung einbezogenen Computer zusammen mit der Korrekturstufe auf.</span><span class="sxs-lookup"><span data-stu-id="8bb43-144">Lists machines included in the investigation along with remediation level.</span></span>|
|<span data-ttu-id="8bb43-145">Wichtige Erkenntnisse</span><span class="sxs-lookup"><span data-stu-id="8bb43-145">Key findings</span></span>   |<span data-ttu-id="8bb43-146">Listet die Ergebnisse der Untersuchung sowie den Status und die ausgeführten oder ausstehenden Aktionen auf.</span><span class="sxs-lookup"><span data-stu-id="8bb43-146">Lists results from the investigation along with status and actions taken or pending.</span></span> <span data-ttu-id="8bb43-147">Sie können ausstehende Aktionen für Geräte und Identitäten auf dieser Registerkarte genehmigen.</span><span class="sxs-lookup"><span data-stu-id="8bb43-147">You can approve pending actions for devices and identities in on this tab.</span></span>|
|<span data-ttu-id="8bb43-148">Entitäten</span><span class="sxs-lookup"><span data-stu-id="8bb43-148">Entities</span></span>   |<span data-ttu-id="8bb43-149">Listet Benutzeraktivitäten, Dateien, Prozesse, Dienste, Treiber, IP-Adressen und Persistenzverfahren im Zusammenhang mit der Untersuchung zusammen mit dem Status und ausgeführten Aktionen auf.</span><span class="sxs-lookup"><span data-stu-id="8bb43-149">Lists user activities, files, processes, services, drivers, IP addresses, and persistence methods associated with the investigation, along with status and actions taken.</span></span>|
|<span data-ttu-id="8bb43-150">Protokoll</span><span class="sxs-lookup"><span data-stu-id="8bb43-150">Log</span></span>    |<span data-ttu-id="8bb43-151">Bietet eine detaillierte Darstellung aller während der Untersuchung ausgeführten Schritte zusammen mit dem Status.</span><span class="sxs-lookup"><span data-stu-id="8bb43-151">Provides a detailed view of all steps taken during the investigation, along with status.</span></span>|
|<span data-ttu-id="8bb43-152">Ausstehende Aktionen</span><span class="sxs-lookup"><span data-stu-id="8bb43-152">Pending actions</span></span>    |<span data-ttu-id="8bb43-153">Listet Elemente auf, für die eine Genehmigung erforderlich, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="8bb43-153">Lists items that require approval to proceed.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="8bb43-154">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8bb43-154">Next steps</span></span>

- [<span data-ttu-id="8bb43-155">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="8bb43-155">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)


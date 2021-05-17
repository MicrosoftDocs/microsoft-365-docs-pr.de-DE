---
title: Anzeigen und Organisieren der Vorfallswarteschlange
ms.reviewer: ''
description: Sehen Sie sich die Liste der Vorfälle an, und erfahren Sie, wie Sie Filter anwenden, um die Liste zu beschränken und eine fokussierte Ansicht zu erhalten.
keywords: view, organize, incidents, aggregate, investigations, queue, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93aa685f12e0241758bf86d3aa956717db052e5f
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499934"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="a1893-104">Anzeigen und Organisieren der Microsoft Defender for Endpoint Incidents-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="a1893-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="a1893-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="a1893-105">**Applies to:**</span></span>
- [<span data-ttu-id="a1893-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="a1893-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="a1893-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a1893-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="a1893-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="a1893-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="a1893-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="a1893-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="a1893-110">Die **Incidents-Warteschlange** zeigt eine Sammlung von Vorfällen an, die von Geräten in Ihrem Netzwerk gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="a1893-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="a1893-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="a1893-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="a1893-112">Standardmäßig werden in der Warteschlange Vorfälle angezeigt, die in den letzten 30 Tagen angezeigt wurden, und der letzte Vorfall wird oben in der Liste angezeigt, damit Sie die neuesten Vorfälle zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="a1893-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="a1893-113">Es stehen mehrere Optionen zur Verfügung, um die Warteschlangenansicht "Vorfälle" anzupassen.</span><span class="sxs-lookup"><span data-stu-id="a1893-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="a1893-114">Im oberen Navigationsbereich können Sie:</span><span class="sxs-lookup"><span data-stu-id="a1893-114">On the top navigation you can:</span></span>
- <span data-ttu-id="a1893-115">Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="a1893-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="a1893-116">Ändern der Anzahl der Elemente, die pro Seite angezeigt werden</span><span class="sxs-lookup"><span data-stu-id="a1893-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="a1893-117">Auswählen der Elemente, die pro Seite angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="a1893-117">Select the items to show per page</span></span>
- <span data-ttu-id="a1893-118">Batchauswahl der zuzuordnenden Vorfälle</span><span class="sxs-lookup"><span data-stu-id="a1893-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="a1893-119">Navigieren zwischen Seiten</span><span class="sxs-lookup"><span data-stu-id="a1893-119">Navigate between pages</span></span>
- <span data-ttu-id="a1893-120">Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="a1893-120">Apply filters</span></span>

![Abbildung einer Vorfallswarteschlange](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="a1893-122">Sortieren und Filtern der Warteschlange für Vorfälle</span><span class="sxs-lookup"><span data-stu-id="a1893-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="a1893-123">Sie können die folgenden Filter anwenden, um die Liste der Vorfälle zu begrenzen und eine fokussierte Ansicht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a1893-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="a1893-124">Severity</span><span class="sxs-lookup"><span data-stu-id="a1893-124">Severity</span></span>

<span data-ttu-id="a1893-125">Schweregrad des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="a1893-125">Incident severity</span></span> | <span data-ttu-id="a1893-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1893-126">Description</span></span>
:---|:---
<span data-ttu-id="a1893-127">Hoch</span><span class="sxs-lookup"><span data-stu-id="a1893-127">High</span></span> </br><span data-ttu-id="a1893-128">(Rot)</span><span class="sxs-lookup"><span data-stu-id="a1893-128">(Red)</span></span> | <span data-ttu-id="a1893-129">Bedrohungen, die häufig mit erweiterten beständigen Bedrohungen (Advanced Persistent Threats, APT) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="a1893-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="a1893-130">Diese Vorfälle deuten auf ein hohes Risiko aufgrund des Schweregrads des Schadens hin, den sie auf Geräten anrichten können.</span><span class="sxs-lookup"><span data-stu-id="a1893-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="a1893-131">Mittel</span><span class="sxs-lookup"><span data-stu-id="a1893-131">Medium</span></span> </br><span data-ttu-id="a1893-132">(Orange)</span><span class="sxs-lookup"><span data-stu-id="a1893-132">(Orange)</span></span> | <span data-ttu-id="a1893-133">Bedrohungen, die in der Organisation selten beobachtet werden, z. B. anomale Registrierungsänderung, Ausführung verdächtiger Dateien und beobachtete Verhaltensweisen, die für Angriffsphasen typisch sind.</span><span class="sxs-lookup"><span data-stu-id="a1893-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="a1893-134">Niedrig</span><span class="sxs-lookup"><span data-stu-id="a1893-134">Low</span></span> </br><span data-ttu-id="a1893-135">(Gelb)</span><span class="sxs-lookup"><span data-stu-id="a1893-135">(Yellow)</span></span> | <span data-ttu-id="a1893-136">Bedrohungen im Zusammenhang mit weit verbreiteter Schadsoftware und Hacktools, die nicht unbedingt auf eine erweiterte Bedrohung für die Organisation hindeuten.</span><span class="sxs-lookup"><span data-stu-id="a1893-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="a1893-137">Zur Information</span><span class="sxs-lookup"><span data-stu-id="a1893-137">Informational</span></span> </br><span data-ttu-id="a1893-138">(Grau)</span><span class="sxs-lookup"><span data-stu-id="a1893-138">(Grey)</span></span> | <span data-ttu-id="a1893-139">Informationsvorfälle werden möglicherweise nicht als schädlich für das Netzwerk betrachtet, aber es ist möglicherweise gut, den Überblick zu behalten.</span><span class="sxs-lookup"><span data-stu-id="a1893-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="a1893-140">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="a1893-140">Assigned to</span></span>
<span data-ttu-id="a1893-141">Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="a1893-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="a1893-142">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a1893-142">Category</span></span>
<span data-ttu-id="a1893-143">Vorfälle werden basierend auf der Beschreibung der Phase kategorisiert, in der sich die Cybersicherheitstötekette befindet.</span><span class="sxs-lookup"><span data-stu-id="a1893-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="a1893-144">Diese Ansicht hilft dem Bedrohungsanalysten bei der Bestimmung der Priorität, Dringlichkeit und der entsprechenden Reaktionsstrategie, die basierend auf dem Kontext bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="a1893-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="a1893-145">Status</span><span class="sxs-lookup"><span data-stu-id="a1893-145">Status</span></span>
<span data-ttu-id="a1893-146">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="a1893-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="a1893-147">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="a1893-147">Data sensitivity</span></span>
<span data-ttu-id="a1893-148">Verwenden Sie diesen Filter, um Vorfälle mit Vertraulichkeitsbezeichnungen zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="a1893-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="a1893-149">Vorfallbenennung</span><span class="sxs-lookup"><span data-stu-id="a1893-149">Incident naming</span></span>

<span data-ttu-id="a1893-150">Um den Umfang des Vorfalls auf einen Blick zu verstehen, werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien generiert.</span><span class="sxs-lookup"><span data-stu-id="a1893-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="a1893-151">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="a1893-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="a1893-152">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, behalten ihren Namen.</span><span class="sxs-lookup"><span data-stu-id="a1893-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="a1893-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1893-153">See also</span></span>
- [<span data-ttu-id="a1893-154">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="a1893-154">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="a1893-155">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="a1893-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="a1893-156">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="a1893-156">Investigate incidents</span></span>](investigate-incidents.md)


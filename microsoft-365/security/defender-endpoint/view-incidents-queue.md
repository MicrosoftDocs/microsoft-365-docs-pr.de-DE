---
title: Anzeigen und Organisieren der Vorfallswarteschlange
ms.reviewer: ''
description: Sehen Sie sich die Liste der Vorfälle an, und erfahren Sie, wie Sie Filter anwenden, um die Liste einzuschränken und eine stärker fokussierte Ansicht zu erhalten.
keywords: anzeigen, organisieren, Vorfälle, aggregieren, Untersuchungen, Warteschlange, ttp
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
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844220"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="d0fd2-104">Anzeigen und Organisieren der Warteschlange für Microsoft Defender für Endpunktvorfälle</span><span class="sxs-lookup"><span data-stu-id="d0fd2-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="d0fd2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d0fd2-105">**Applies to:**</span></span>
- [<span data-ttu-id="d0fd2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="d0fd2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="d0fd2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d0fd2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d0fd2-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="d0fd2-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d0fd2-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="d0fd2-110">Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die von Geräten in Ihrem Netzwerk gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="d0fd2-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="d0fd2-112">Standardmäßig zeigt die Warteschlange Vorfälle an, die in den letzten 30 Tagen aufgetreten sind, wobei der letzte Vorfall oben in der Liste angezeigt wird, damit Sie die neuesten Vorfälle zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="d0fd2-113">Es gibt mehrere Optionen, aus denen Sie auswählen können, um die Vorfallwarteschlangenansicht anzupassen.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="d0fd2-114">In der oberen Navigationsleiste haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="d0fd2-114">On the top navigation you can:</span></span>
- <span data-ttu-id="d0fd2-115">Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="d0fd2-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="d0fd2-116">Ändern der Anzahl der Elemente, die pro Seite angezeigt werden sollen</span><span class="sxs-lookup"><span data-stu-id="d0fd2-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="d0fd2-117">Auswählen der Elemente, die pro Seite angezeigt werden sollen</span><span class="sxs-lookup"><span data-stu-id="d0fd2-117">Select the items to show per page</span></span>
- <span data-ttu-id="d0fd2-118">Batchauswahl der zuzuweisenden Vorfälle</span><span class="sxs-lookup"><span data-stu-id="d0fd2-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="d0fd2-119">Navigieren zwischen Seiten</span><span class="sxs-lookup"><span data-stu-id="d0fd2-119">Navigate between pages</span></span>
- <span data-ttu-id="d0fd2-120">Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="d0fd2-120">Apply filters</span></span>

![Abbildung einer Vorfallswarteschlange](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="d0fd2-122">Sortieren und Filtern der Vorfallwarteschlange</span><span class="sxs-lookup"><span data-stu-id="d0fd2-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="d0fd2-123">Sie können die folgenden Filter anwenden, um die Liste der Vorfälle einzuschränken und eine stärker fokussierte Ansicht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="d0fd2-124">Severity</span><span class="sxs-lookup"><span data-stu-id="d0fd2-124">Severity</span></span>

<span data-ttu-id="d0fd2-125">Schweregrad des Vorfalls</span><span class="sxs-lookup"><span data-stu-id="d0fd2-125">Incident severity</span></span> | <span data-ttu-id="d0fd2-126">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d0fd2-126">Description</span></span>
:---|:---
<span data-ttu-id="d0fd2-127">Hoch</span><span class="sxs-lookup"><span data-stu-id="d0fd2-127">High</span></span> </br><span data-ttu-id="d0fd2-128">(Rot)</span><span class="sxs-lookup"><span data-stu-id="d0fd2-128">(Red)</span></span> | <span data-ttu-id="d0fd2-129">Bedrohungen, die häufig mit erweiterten dauerhaften Bedrohungen (Advanced Persistent Threats, APT) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="d0fd2-130">Diese Vorfälle weisen aufgrund des Schweregrads des Schadens, den sie auf Geräten verursachen können, auf ein hohes Risiko hin.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="d0fd2-131">Mittel</span><span class="sxs-lookup"><span data-stu-id="d0fd2-131">Medium</span></span> </br><span data-ttu-id="d0fd2-132">(Orange)</span><span class="sxs-lookup"><span data-stu-id="d0fd2-132">(Orange)</span></span> | <span data-ttu-id="d0fd2-133">Bedrohungen, die in der Organisation selten beobachtet werden, z. B. anomale Registrierungsänderungen, Ausführung verdächtiger Dateien und beobachtete Verhaltensweisen, die typisch für Angriffsphasen sind.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="d0fd2-134">Niedrig</span><span class="sxs-lookup"><span data-stu-id="d0fd2-134">Low</span></span> </br><span data-ttu-id="d0fd2-135">(Gelb)</span><span class="sxs-lookup"><span data-stu-id="d0fd2-135">(Yellow)</span></span> | <span data-ttu-id="d0fd2-136">Bedrohungen im Zusammenhang mit weit verbreiteter Schadsoftware und Hack-Tools, die nicht notwendigerweise auf eine erweiterte Bedrohung für die Organisation hinweisen.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="d0fd2-137">Zur Information</span><span class="sxs-lookup"><span data-stu-id="d0fd2-137">Informational</span></span> </br><span data-ttu-id="d0fd2-138">(Grau)</span><span class="sxs-lookup"><span data-stu-id="d0fd2-138">(Grey)</span></span> | <span data-ttu-id="d0fd2-139">Informationsvorfälle werden möglicherweise nicht als schädlich für das Netzwerk betrachtet, können aber gut nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="d0fd2-140">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="d0fd2-140">Assigned to</span></span>
<span data-ttu-id="d0fd2-141">Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="d0fd2-142">Kategorie</span><span class="sxs-lookup"><span data-stu-id="d0fd2-142">Category</span></span>
<span data-ttu-id="d0fd2-143">Vorfälle werden basierend auf der Beschreibung der Phase kategorisiert, in der sich die Cybersicherheits-Kill Chain befindet.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="d0fd2-144">Diese Ansicht hilft dem Bedrohungsanalysten, Priorität, Dringlichkeit und entsprechende Reaktionsstrategie zu bestimmen, die basierend auf dem Kontext bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="d0fd2-145">Status</span><span class="sxs-lookup"><span data-stu-id="d0fd2-145">Status</span></span>
<span data-ttu-id="d0fd2-146">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="d0fd2-147">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="d0fd2-147">Data sensitivity</span></span>
<span data-ttu-id="d0fd2-148">Verwenden Sie diesen Filter, um Vorfälle anzuzeigen, die Vertraulichkeitsbezeichnungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="d0fd2-149">Benennung von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d0fd2-149">Incident naming</span></span>

<span data-ttu-id="d0fd2-150">Um den Umfang des Vorfalls auf einen Blick zu verstehen, werden Vorfallnamen automatisch basierend auf Warnungsattributen wie der Anzahl der betroffenen Endpunkte, betroffenen Benutzern, Erkennungsquellen oder Kategorien generiert.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="d0fd2-151">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="d0fd2-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="d0fd2-152">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen aufgetreten sind, behalten ihren Namen.</span><span class="sxs-lookup"><span data-stu-id="d0fd2-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="d0fd2-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0fd2-153">See also</span></span>
- [<span data-ttu-id="d0fd2-154">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="d0fd2-154">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="d0fd2-155">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d0fd2-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="d0fd2-156">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d0fd2-156">Investigate incidents</span></span>](investigate-incidents.md)


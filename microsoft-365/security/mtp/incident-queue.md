---
title: Priorisieren von Vorfällen in Microsoft Threat Protection
description: Erfahren Sie, wie Sie Vorfälle in der Vorfallswarteschlange in Microsoft Threat Protection priorisieren können.
keywords: Vorfall, Warteschlange, Übersicht, Geräte, Identitäten, Benutzer, Postfach, E-Mail, Vorfälle
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d827484a440b291bccd45b58e977fbcb280680f2
ms.sourcegitcommit: 94f2f8e3e6bc3946d8b3cf798b3eb77a49ffd12a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2020
ms.locfileid: "45148136"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="b8308-104">Priorisieren von Vorfällen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8308-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="b8308-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b8308-105">**Applies to:**</span></span>
- <span data-ttu-id="b8308-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="b8308-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="b8308-107">Microsoft Threat Protection wendet Korrelationsanalysen an und fasst alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einem einzigen Vorfall zusammen.</span><span class="sxs-lookup"><span data-stu-id="b8308-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="b8308-108">Microsoft Threat Protection löst auch eindeutige Warnungen zu Aktivitäten aus, die nur aufgrund der umfassenden Transparenz von Microsoft Threat Protection über das gesamte System und die gesamte Suite von Produkten als bösartig erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="b8308-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="b8308-109">Auf diese Weise kommentiert Microsoft Threat Protection die umfassendere Angriffsgeschichte, sodass ein Analyst für Sicherheitsoperationen komplexe Bedrohungen in der gesamten Organisation erkennen und bewältigen kann.</span><span class="sxs-lookup"><span data-stu-id="b8308-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="b8308-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="b8308-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="b8308-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="b8308-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

<span data-ttu-id="b8308-113">Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten 30 Tagen aufgetreten sind, wobei der letzte Vorfall am Anfang der Liste angezeigt wird, sodass Sie die neuesten Vorfälle zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="b8308-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="b8308-114">Die Vorfallswarteschlange bietet anpassbare Spalten, die Ihnen einen Einblick in die unterschiedlichen Merkmale des Vorfalls oder in die enthaltenen Entitäten verschaffen, und Ihnen helfen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="b8308-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="b8308-115">Um einen Überblick zu erhalten, werden bei der automatischen Benennung von Anteilen, die sich derzeit in der öffentlichen Vorschau befinden, Vorfall Namen basierend auf Warnungs Attributen generiert, beispielsweise die Anzahl betroffener Endpunkte, betroffene Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="b8308-115">For additional visibility at-a-glance, automatic incident naming, currently in public preview, generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="b8308-116">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="b8308-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="b8308-117">Beispiel: *mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="b8308-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="b8308-118">Bei Vorfällen, die vor dem Rollout der automatischen Vorfall Benennung vorhanden waren, wird der Name nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="b8308-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="b8308-119">Erfahren Sie mehr über das [Aktivieren von Vorschaufunktionen](preview.md#turn-on-preview-features).</span><span class="sxs-lookup"><span data-stu-id="b8308-119">Learn more about [turning on preview features](preview.md#turn-on-preview-features).</span></span>

<span data-ttu-id="b8308-120">Die Vorfallswarteschlange stellt außerdem mehrere Filteroptionen zur Verfügung. Wenn diese angewendet werden, können Sie auswählen, ob Sie alle vorhandenen Vorfälle in Ihrer Umgebung umfassend aufräumen oder sich auf ein bestimmtes Szenario oder eine Bedrohung konzentrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="b8308-120">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="b8308-121">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="b8308-121">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="b8308-122">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="b8308-122">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="b8308-123">Status</span><span class="sxs-lookup"><span data-stu-id="b8308-123">Status</span></span>
<span data-ttu-id="b8308-124">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="b8308-124">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="b8308-125">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="b8308-125">Severity</span></span>
<span data-ttu-id="b8308-126">Der Schweregrad eines Vorfalls ist ein Indikator für die Auswirkungen, die dieser bei Ihnen haben kann.</span><span class="sxs-lookup"><span data-stu-id="b8308-126">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="b8308-127">Je höher der Schweregrad, desto größer die Auswirkungen. In der Regel ist bei einem höheren Schweregrad auch die größte sofortige Aufmerksamkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b8308-127">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="b8308-128">Zugewiesen zu (Benutzer)</span><span class="sxs-lookup"><span data-stu-id="b8308-128">Assigned to (owner)</span></span>
<span data-ttu-id="b8308-129">Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="b8308-129">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="b8308-130">Mehrere Warnungen</span><span class="sxs-lookup"><span data-stu-id="b8308-130">Multiple alerts</span></span> 
<span data-ttu-id="b8308-131">Filtern Sie, um nur Vorfälle mit mehr als einer Warnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b8308-131">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="b8308-132">Dies kann ein Anzeichen für einen Angriff sein, der komplexer oder in der Kill Chain weiter fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="b8308-132">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="b8308-133">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="b8308-133">Multiple service sources</span></span> 
<span data-ttu-id="b8308-134">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="b8308-134">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="b8308-135">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="b8308-135">Service sources</span></span>
<span data-ttu-id="b8308-136">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8308-136">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="b8308-137">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="b8308-137">Multiple categories</span></span> 
<span data-ttu-id="b8308-138">Sie können auswählen, dass nur Vorfälle angezeigt werden sollen, die mehreren Kategorien der Kill Chain zugeordnet sind und möglicherweise zu weiteren Beschädigungen führen können.</span><span class="sxs-lookup"><span data-stu-id="b8308-138">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="b8308-139">Kategorien</span><span class="sxs-lookup"><span data-stu-id="b8308-139">Categories</span></span>
<span data-ttu-id="b8308-140">Wählen Sie bestimmte Kategorien aus, um sich auf einen bestimmten Schritt in der Kill Chain zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="b8308-140">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="b8308-141">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="b8308-141">Data sensitivity</span></span>
<span data-ttu-id="b8308-142">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="b8308-142">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="b8308-143">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="b8308-143">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="b8308-144">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="b8308-144">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="b8308-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b8308-145">Next steps</span></span>
<span data-ttu-id="b8308-146">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="b8308-146">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="b8308-147">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b8308-147">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="b8308-148">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b8308-148">Related topics</span></span>
- [<span data-ttu-id="b8308-149">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="b8308-149">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="b8308-150">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b8308-150">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="b8308-151">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="b8308-151">Manage incidents</span></span>](manage-incidents.md)

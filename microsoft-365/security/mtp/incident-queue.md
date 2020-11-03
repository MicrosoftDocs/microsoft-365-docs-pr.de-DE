---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Priorisieren von Vorfällen von der Vorfall Warteschlange in Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f681d02cc4af8bd56ba945a3d944798e545bf93c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846712"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="64feb-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64feb-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="64feb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64feb-105">**Applies to:**</span></span>
- <span data-ttu-id="64feb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64feb-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="64feb-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten zu einem einzigen Vorfall.</span><span class="sxs-lookup"><span data-stu-id="64feb-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="64feb-108">Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die nur als böswillig identifiziert werden können, wenn die End-to-End-Sichtbarkeit vorliegt, die Microsoft 365 Defender über das gesamte Anwesen und die Produktsuite verfügt.</span><span class="sxs-lookup"><span data-stu-id="64feb-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="64feb-109">Auf diese Weise erzählt Microsoft 365 Defender die breitere Angriffs Geschichte, sodass ein Security Operations Analyst komplexe Bedrohungen in der gesamten Organisation verstehen und bewältigen kann.</span><span class="sxs-lookup"><span data-stu-id="64feb-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="64feb-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="64feb-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="64feb-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="64feb-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

<span data-ttu-id="64feb-113">Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten 30 Tagen aufgetreten sind, wobei der letzte Vorfall am Anfang der Liste angezeigt wird, sodass Sie die neuesten Vorfälle zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="64feb-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="64feb-114">Die Vorfallswarteschlange bietet anpassbare Spalten, die Ihnen einen Einblick in die unterschiedlichen Merkmale des Vorfalls oder in die enthaltenen Entitäten verschaffen, und Ihnen helfen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="64feb-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="64feb-115">Um eine zusätzliche Sichtbarkeit auf einen Blick zu erhalten, werden bei der automatischen Benennung von Ereignissen Vorfall Namen basierend auf Warnungs Attributen generiert, beispielsweise die Anzahl betroffener Endpunkte, betroffene Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="64feb-115">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="64feb-116">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="64feb-116">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="64feb-117">Beispiel: *mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="64feb-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="64feb-118">Bei Vorfällen, die vor dem Rollout der automatischen Vorfall Benennung vorhanden waren, wird der Name nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="64feb-118">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="64feb-119">Die Vorfallswarteschlange stellt außerdem mehrere Filteroptionen zur Verfügung. Wenn diese angewendet werden, können Sie auswählen, ob Sie alle vorhandenen Vorfälle in Ihrer Umgebung umfassend aufräumen oder sich auf ein bestimmtes Szenario oder eine Bedrohung konzentrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="64feb-119">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="64feb-120">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="64feb-120">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="64feb-121">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="64feb-121">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="64feb-122">Status</span><span class="sxs-lookup"><span data-stu-id="64feb-122">Status</span></span>
<span data-ttu-id="64feb-123">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="64feb-123">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="64feb-124">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="64feb-124">Severity</span></span>
<span data-ttu-id="64feb-125">Der Schweregrad eines Vorfalls ist ein Indikator für die Auswirkungen, die dieser bei Ihnen haben kann.</span><span class="sxs-lookup"><span data-stu-id="64feb-125">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="64feb-126">Je höher der Schweregrad, desto größer die Auswirkungen. In der Regel ist bei einem höheren Schweregrad auch die größte sofortige Aufmerksamkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64feb-126">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="64feb-127">Zugewiesen zu (Benutzer)</span><span class="sxs-lookup"><span data-stu-id="64feb-127">Assigned to (owner)</span></span>
<span data-ttu-id="64feb-128">Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="64feb-128">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="64feb-129">Mehrere Warnungen</span><span class="sxs-lookup"><span data-stu-id="64feb-129">Multiple alerts</span></span> 
<span data-ttu-id="64feb-130">Filtern Sie, um nur Vorfälle mit mehr als einer Warnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="64feb-130">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="64feb-131">Dies kann ein Anzeichen für einen Angriff sein, der komplexer oder in der Kill Chain weiter fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="64feb-131">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="64feb-132">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="64feb-132">Multiple service sources</span></span> 
<span data-ttu-id="64feb-133">Filtern, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span><span class="sxs-lookup"><span data-stu-id="64feb-133">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365)</span></span>
### <a name="service-sources"></a><span data-ttu-id="64feb-134">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="64feb-134">Service sources</span></span>
<span data-ttu-id="64feb-135">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="64feb-135">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="64feb-136">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="64feb-136">Multiple categories</span></span> 
<span data-ttu-id="64feb-137">Sie können auswählen, dass nur Vorfälle angezeigt werden sollen, die mehreren Kategorien der Kill Chain zugeordnet sind und möglicherweise zu weiteren Beschädigungen führen können.</span><span class="sxs-lookup"><span data-stu-id="64feb-137">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="64feb-138">Kategorien</span><span class="sxs-lookup"><span data-stu-id="64feb-138">Categories</span></span>
<span data-ttu-id="64feb-139">Wählen Sie bestimmte Kategorien aus, um sich auf einen bestimmten Schritt in der Kill Chain zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="64feb-139">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="64feb-140">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="64feb-140">Data sensitivity</span></span>
<span data-ttu-id="64feb-141">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="64feb-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="64feb-142">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="64feb-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="64feb-143">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="64feb-143">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="64feb-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="64feb-144">Next steps</span></span>
<span data-ttu-id="64feb-145">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="64feb-145">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="64feb-146">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="64feb-146">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="64feb-147">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="64feb-147">Related topics</span></span>
- [<span data-ttu-id="64feb-148">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="64feb-148">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="64feb-149">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="64feb-149">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="64feb-150">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="64feb-150">Manage incidents</span></span>](manage-incidents.md)

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
ms.openlocfilehash: 4369d51ed740af652be632ba0b8752c708d6c719
ms.sourcegitcommit: b64f36d3873fa0041b24bec029deb73ccfdfdbac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48877219"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="f8536-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8536-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f8536-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f8536-105">**Applies to:**</span></span>
- <span data-ttu-id="f8536-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8536-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="f8536-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten zu einem einzigen Vorfall.</span><span class="sxs-lookup"><span data-stu-id="f8536-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="f8536-108">Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die nur als böswillig identifiziert werden können, wenn die End-to-End-Sichtbarkeit vorliegt, die Microsoft 365 Defender über das gesamte Anwesen und die Produktsuite verfügt.</span><span class="sxs-lookup"><span data-stu-id="f8536-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="f8536-109">Auf diese Weise erzählt Microsoft 365 Defender die breitere Angriffs Geschichte, sodass ein Security Operations Analyst komplexe Bedrohungen in der gesamten Organisation verstehen und bewältigen kann.</span><span class="sxs-lookup"><span data-stu-id="f8536-109">By doing so, Microsoft 365 Defender narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="f8536-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="f8536-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="f8536-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="f8536-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

<span data-ttu-id="f8536-113">Standardmäßig zeigt die Warteschlange im Microsoft 365 Security Center Vorfälle an, die in den letzten 30 Tagen angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="f8536-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="f8536-114">Der letzte Vorfall befindet sich am Anfang der Liste, sodass Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="f8536-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="f8536-115">Die Vorfall Warteschlange macht anpassbare Spalten verfügbar, mit denen Sie die verschiedenen Merkmale des Vorfalls oder die enthaltenen Entitäten sichtbar machen können.</span><span class="sxs-lookup"><span data-stu-id="f8536-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="f8536-116">Auf diese Weise können Sie eine fundierte Entscheidung in Bezug auf die Priorisierung von Vorfällen für die Verarbeitung treffen.</span><span class="sxs-lookup"><span data-stu-id="f8536-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="f8536-117">Um eine zusätzliche Sichtbarkeit auf einen Blick zu erhalten, werden bei der automatischen Benennung von Ereignissen Vorfall Namen basierend auf Warnungs Attributen generiert, beispielsweise die Anzahl betroffener Endpunkte, betroffene Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="f8536-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="f8536-118">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="f8536-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="f8536-119">Beispiel: *mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="f8536-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="f8536-120">Bei Vorfällen, die vor dem Rollout der automatischen Vorfall Benennung vorhanden waren, wird der Name nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="f8536-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="f8536-121">Die Vorfall Warteschlange macht auch mehrere Filteroptionen verfügbar, die Ihnen bei Anwendung die Möglichkeit bieten, eine umfassende Bereinigung aller vorhandenen Vorfälle in Ihrer Umgebung durchzuführen oder sich auf ein bestimmtes Szenario oder eine Bedrohung konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="f8536-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="f8536-122">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f8536-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="f8536-123">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="f8536-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="f8536-124">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="f8536-124">Assigned to</span></span>
<span data-ttu-id="f8536-125">Sie können festlegen, dass Warnungen angezeigt werden, die Ihnen zugewiesen sind oder die von Automatisierung behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="f8536-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="f8536-126">Categories</span><span class="sxs-lookup"><span data-stu-id="f8536-126">Categories</span></span>
<span data-ttu-id="f8536-127">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffs Komponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="f8536-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="f8536-128">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="f8536-128">Classification</span></span>
<span data-ttu-id="f8536-129">Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="f8536-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="f8536-130">Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f8536-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="f8536-131">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="f8536-131">Data sensitivity</span></span>
<span data-ttu-id="f8536-132">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="f8536-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="f8536-133">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="f8536-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="f8536-134">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f8536-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="f8536-135">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="f8536-135">Device group</span></span>
<span data-ttu-id="f8536-136">Filtern nach definierten Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="f8536-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="f8536-137">Untersuchungs Zustand</span><span class="sxs-lookup"><span data-stu-id="f8536-137">Investigation state</span></span>
<span data-ttu-id="f8536-138">Filtern von Vorfällen nach dem Status der automatischen Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="f8536-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="f8536-139">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="f8536-139">Multiple categories</span></span> 
<span data-ttu-id="f8536-140">Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden anrichten können.</span><span class="sxs-lookup"><span data-stu-id="f8536-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="f8536-141">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="f8536-141">Multiple service sources</span></span> 
<span data-ttu-id="f8536-142">Filtern, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="f8536-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="f8536-143">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="f8536-143">OS platform</span></span>
<span data-ttu-id="f8536-144">Einschränken der Vorfall Warteschlangenansicht nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="f8536-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="f8536-145">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="f8536-145">Service sources</span></span>
<span data-ttu-id="f8536-146">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="f8536-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="f8536-147">Severity</span><span class="sxs-lookup"><span data-stu-id="f8536-147">Severity</span></span>
<span data-ttu-id="f8536-148">Der Schweregrad eines Vorfalls deutet auf die Auswirkungen hin, die er auf Ihre Objekte haben kann.</span><span class="sxs-lookup"><span data-stu-id="f8536-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="f8536-149">Je höher der Schweregrad, desto größer ist die Auswirkung und erfordert in der Regel die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="f8536-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="f8536-150">Status</span><span class="sxs-lookup"><span data-stu-id="f8536-150">Status</span></span>
<span data-ttu-id="f8536-151">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="f8536-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f8536-152">Die Filter "Klassifizierung", "Gerätegruppe", "Ermittlungsstatus" und "BS-Plattform" sind derzeit nur in der öffentlichen Vorschau verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f8536-152">The Classification, Device group, Investigation state, and OS platform filters are currently only available in public preview.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f8536-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f8536-153">Next steps</span></span>
<span data-ttu-id="f8536-154">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="f8536-154">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="f8536-155">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f8536-155">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="f8536-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8536-156">See also</span></span>
- [<span data-ttu-id="f8536-157">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="f8536-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="f8536-158">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f8536-158">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="f8536-159">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="f8536-159">Manage incidents</span></span>](manage-incidents.md)

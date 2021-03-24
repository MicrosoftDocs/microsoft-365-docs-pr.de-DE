---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Filtern von Vorfällen aus der Vorfallwarteschlange in Microsoft 365 Defender
keywords: Vorfall, Warteschlange, Übersicht, Geräte, Identitäten, Benutzer, Postfach, E-Mail, Vorfälle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 0683e0f2c9f4d46b3b644e2fec882a126aaab9b9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062023"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="03801-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03801-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="03801-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="03801-105">**Applies to:**</span></span>
- <span data-ttu-id="03801-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03801-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="03801-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="03801-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="03801-108">Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die nur aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Immobilie und Produktsuite verfügt, als bösartig identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="03801-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="03801-109">Diese Ansicht bietet Ihrem Sicherheitsbetriebsanalysten die umfassendere Angriffsgeschichte, die ihnen hilft, komplexe Bedrohungen in der gesamten Organisation besser zu verstehen und zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="03801-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="03801-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="03801-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="03801-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="03801-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

<span data-ttu-id="03801-113">Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten 30 Tagen angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="03801-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="03801-114">Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="03801-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="03801-115">Die Vorfallwarteschlange macht anpassbare Spalten verfügbar, die Ihnen Einblick in unterschiedliche Merkmale des Vorfalls oder der enthaltenen Entitäten bieten.</span><span class="sxs-lookup"><span data-stu-id="03801-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="03801-116">Dies hilft Ihnen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="03801-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="03801-117">Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="03801-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="03801-118">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="03801-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="03801-119">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="03801-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="03801-120">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="03801-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="03801-121">Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie bei Anwendung eine umfassende Auswahl aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="03801-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="03801-122">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="03801-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="03801-123">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="03801-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="03801-124">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="03801-124">Assigned to</span></span>
<span data-ttu-id="03801-125">Sie können Warnungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="03801-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="03801-126">Categories</span><span class="sxs-lookup"><span data-stu-id="03801-126">Categories</span></span>
<span data-ttu-id="03801-127">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="03801-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="03801-128">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="03801-128">Classification</span></span>
<span data-ttu-id="03801-129">Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="03801-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="03801-130">Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="03801-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="03801-131">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="03801-131">Data sensitivity</span></span>
<span data-ttu-id="03801-132">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="03801-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="03801-133">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="03801-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="03801-134">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="03801-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="03801-135">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="03801-135">Device group</span></span>
<span data-ttu-id="03801-136">Nach definierten Gerätegruppen filtern.</span><span class="sxs-lookup"><span data-stu-id="03801-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="03801-137">Untersuchungsstatus</span><span class="sxs-lookup"><span data-stu-id="03801-137">Investigation state</span></span>
<span data-ttu-id="03801-138">Filtern von Vorfällen nach dem Status der automatisierten Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="03801-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="03801-139">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="03801-139">Multiple categories</span></span> 
<span data-ttu-id="03801-140">Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können.</span><span class="sxs-lookup"><span data-stu-id="03801-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="03801-141">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="03801-141">Multiple service sources</span></span> 
<span data-ttu-id="03801-142">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="03801-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="03801-143">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="03801-143">OS platform</span></span>
<span data-ttu-id="03801-144">Beschränken Sie die Vorfallwarteschlange nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="03801-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="03801-145">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="03801-145">Service sources</span></span>
<span data-ttu-id="03801-146">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="03801-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="03801-147">Severity</span><span class="sxs-lookup"><span data-stu-id="03801-147">Severity</span></span>
<span data-ttu-id="03801-148">Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann.</span><span class="sxs-lookup"><span data-stu-id="03801-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="03801-149">Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="03801-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="03801-150">Status</span><span class="sxs-lookup"><span data-stu-id="03801-150">Status</span></span>
<span data-ttu-id="03801-151">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="03801-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="03801-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="03801-152">Next steps</span></span>
<span data-ttu-id="03801-153">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="03801-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="03801-154">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="03801-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="03801-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03801-155">See also</span></span>
- [<span data-ttu-id="03801-156">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="03801-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="03801-157">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="03801-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="03801-158">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="03801-158">Manage incidents</span></span>](manage-incidents.md)

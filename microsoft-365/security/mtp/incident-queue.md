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
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929294"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="094f5-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="094f5-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="094f5-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="094f5-105">**Applies to:**</span></span>
- <span data-ttu-id="094f5-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="094f5-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="094f5-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="094f5-107">Microsoft 365 Defender applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="094f5-108">Microsoft 365 Defender löst auch eindeutige Warnungen zu Aktivitäten aus, die nur aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über das gesamte Land und die gesamte Produktsuite verfügt, als bösartig identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="094f5-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire estate and suite of products.</span></span> <span data-ttu-id="094f5-109">Diese Ansicht gibt Ihrem Analysten für Sicherheitsvorgänge die umfassendere Angriffsgeschichte, die ihnen dabei hilft, komplexe Bedrohungen in der gesamten Organisation besser zu verstehen und zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="094f5-109">This view gives your security operations analyst the broader attack story, which helps them better understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="094f5-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="094f5-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="094f5-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="094f5-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../../media/incidents-queue.png) 

<span data-ttu-id="094f5-113">Standardmäßig zeigt die Warteschlange im Microsoft 365 Security Center Vorfälle an, die in den letzten 30 Tagen angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="094f5-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days.</span></span> <span data-ttu-id="094f5-114">Der letzte Vorfall steht ganz oben in der Liste, damit Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="094f5-114">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="094f5-115">Die Vorfallwarteschlange macht anpassbare Spalten verfügbar, die Ihnen Einblicke in unterschiedliche Merkmale des Vorfalls oder der enthaltenen Entitäten bieten.</span><span class="sxs-lookup"><span data-stu-id="094f5-115">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities.</span></span> <span data-ttu-id="094f5-116">Auf diese Weise können Sie fundierte Entscheidungen zur Priorisierung von Vorfällen treffen, die sie behandeln müssen.</span><span class="sxs-lookup"><span data-stu-id="094f5-116">This helps you make an informed decision regarding prioritization of incidents to handle.</span></span>

<span data-ttu-id="094f5-117">Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl der betroffenen Endpunkte, der betroffenen Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="094f5-117">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="094f5-118">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="094f5-118">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="094f5-119">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="094f5-119">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="094f5-120">Bei Vorfällen, die vor der Einführung der automatischen Benennung von Vorfällen vorhanden waren, wird ihr Name nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="094f5-120">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="094f5-121">Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie, wenn sie angewendet wird, eine umfassende Aufrierung aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich entscheiden können, sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="094f5-121">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="094f5-122">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="094f5-122">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="094f5-123">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="094f5-123">Available filters</span></span>

### <a name="assigned-to"></a><span data-ttu-id="094f5-124">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="094f5-124">Assigned to</span></span>
<span data-ttu-id="094f5-125">Sie können auswählen, ob Sie Warnungen anzeigen möchten, die Ihnen zugewiesen sind oder die von der Automatisierung behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="094f5-125">You can choose to show alerts that are assigned to you or those handled by automation.</span></span>

### <a name="categories"></a><span data-ttu-id="094f5-126">Kategorien</span><span class="sxs-lookup"><span data-stu-id="094f5-126">Categories</span></span>
<span data-ttu-id="094f5-127">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="094f5-127">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> 

### <a name="classification"></a><span data-ttu-id="094f5-128">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="094f5-128">Classification</span></span>
<span data-ttu-id="094f5-129">Filtern Sie Vorfälle basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="094f5-129">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="094f5-130">Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegte.</span><span class="sxs-lookup"><span data-stu-id="094f5-130">The values include true alerts, false alerts, or not set.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="094f5-131">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="094f5-131">Data sensitivity</span></span>
<span data-ttu-id="094f5-132">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="094f5-132">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="094f5-133">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="094f5-133">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="094f5-134">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="094f5-134">Only applicable if Microsoft Information Protection is turned on.</span></span>

### <a name="device-group"></a><span data-ttu-id="094f5-135">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="094f5-135">Device group</span></span>
<span data-ttu-id="094f5-136">Nach definierten Gerätegruppen filtern.</span><span class="sxs-lookup"><span data-stu-id="094f5-136">Filter by defined device groups.</span></span>

### <a name="investigation-state"></a><span data-ttu-id="094f5-137">Untersuchungsstatus</span><span class="sxs-lookup"><span data-stu-id="094f5-137">Investigation state</span></span>
<span data-ttu-id="094f5-138">Filtern Sie Vorfälle nach dem Status der automatischen Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="094f5-138">Filter incidents by the status of automated investigation.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="094f5-139">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="094f5-139">Multiple categories</span></span> 
<span data-ttu-id="094f5-140">Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können.</span><span class="sxs-lookup"><span data-stu-id="094f5-140">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> 

### <a name="multiple-service-sources"></a><span data-ttu-id="094f5-141">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="094f5-141">Multiple service sources</span></span> 
<span data-ttu-id="094f5-142">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus verschiedenen Quellen enthalten (Microsoft Defender für Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="094f5-142">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span>

### <a name="os-platform"></a><span data-ttu-id="094f5-143">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="094f5-143">OS platform</span></span>
<span data-ttu-id="094f5-144">Beschränken Sie die Vorfallwarteschlange nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="094f5-144">Limit the incident queue view by operating system.</span></span>

### <a name="service-sources"></a><span data-ttu-id="094f5-145">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="094f5-145">Service sources</span></span>
<span data-ttu-id="094f5-146">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="094f5-146">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="severity"></a><span data-ttu-id="094f5-147">Severity</span><span class="sxs-lookup"><span data-stu-id="094f5-147">Severity</span></span>
<span data-ttu-id="094f5-148">Der Schweregrad eines Vorfalls ist ein Hinweis auf die Auswirkungen, die er auf Ihre Ressourcen haben kann.</span><span class="sxs-lookup"><span data-stu-id="094f5-148">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="094f5-149">Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die direkteste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="094f5-149">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="status"></a><span data-ttu-id="094f5-150">Status</span><span class="sxs-lookup"><span data-stu-id="094f5-150">Status</span></span>
<span data-ttu-id="094f5-151">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="094f5-151">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>




## <a name="next-steps"></a><span data-ttu-id="094f5-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="094f5-152">Next steps</span></span>
<span data-ttu-id="094f5-153">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="094f5-153">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="094f5-154">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="094f5-154">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="see-also"></a><span data-ttu-id="094f5-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="094f5-155">See also</span></span>
- [<span data-ttu-id="094f5-156">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="094f5-156">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="094f5-157">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="094f5-157">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="094f5-158">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="094f5-158">Manage incidents</span></span>](manage-incidents.md)

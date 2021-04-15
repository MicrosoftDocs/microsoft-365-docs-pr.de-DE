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
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 12207d69b0a1565caf762a265c1a0d32158ca291
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51759850"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="01795-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01795-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="01795-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="01795-105">**Applies to:**</span></span>
- <span data-ttu-id="01795-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01795-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="01795-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten in einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="01795-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="01795-108">Microsoft 365 Defender löst auch eindeutige Warnungen zu Aktivitäten aus, die nur als bösartig identifiziert werden können, wenn die End-to-End-Sichtbarkeit von Microsoft 365 Defender für die gesamte Produktsuite gilt.</span><span class="sxs-lookup"><span data-stu-id="01795-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="01795-109">Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsgeschichte, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="01795-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="01795-110">Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die über Geräte, Benutzer und Postfächer hinweg erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="01795-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="01795-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="01795-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="01795-112">Beim Schnellstart des  Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)) & Warnungen > Vorfällen in die Warteschleife.</span><span class="sxs-lookup"><span data-stu-id="01795-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

<span data-ttu-id="01795-114">Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten sechs Monaten beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="01795-114">By default, the queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="01795-115">Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="01795-115">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="01795-116">Die Vorfallwarteschlange verfügt über anpassbare Spalten **(wählen** Sie Spalten auswählen) aus, die Ihnen Einblicke in verschiedene Merkmale des Vorfalls oder der betroffenen Entitäten bieten.</span><span class="sxs-lookup"><span data-stu-id="01795-116">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="01795-117">Dies hilft Ihnen, eine fundierte Entscheidung über die Priorisierung von Vorfällen für Anaylsis zu treffen.</span><span class="sxs-lookup"><span data-stu-id="01795-117">This helps you make an informed decision regarding the prioritization of incidents for anaylsis.</span></span>

<span data-ttu-id="01795-118">Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="01795-118">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="01795-119">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="01795-119">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="01795-120">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="01795-120">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="01795-121">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="01795-121">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="01795-122">Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie bei Anwendung eine umfassende Auswahl aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="01795-122">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="01795-123">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="01795-123">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="01795-124">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="01795-124">Available filters</span></span>

<span data-ttu-id="01795-125">In der Standardwarteschlange für Vorfälle können Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie einen gefilterten Satz von Vorfällen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="01795-125">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="01795-126">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="01795-126">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

<span data-ttu-id="01795-128">In dieser Tabelle sind die verfügbaren Filternamen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="01795-128">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="01795-129">Filtername</span><span class="sxs-lookup"><span data-stu-id="01795-129">Filter name</span></span> | <span data-ttu-id="01795-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="01795-130">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="01795-131">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="01795-131">Assigned to</span></span> | <span data-ttu-id="01795-132">Sie können Warnungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="01795-132">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="01795-133">Kategorien</span><span class="sxs-lookup"><span data-stu-id="01795-133">Categories</span></span> | <span data-ttu-id="01795-134">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="01795-134">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="01795-135">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="01795-135">Classification</span></span> | <span data-ttu-id="01795-136">Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="01795-136">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="01795-137">Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="01795-137">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="01795-138">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="01795-138">Data sensitivity</span></span> | <span data-ttu-id="01795-139">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="01795-139">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="01795-140">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="01795-140">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="01795-141">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="01795-141">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="01795-142">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="01795-142">Device group</span></span> | <span data-ttu-id="01795-143">Nach definierten Gerätegruppen filtern.</span><span class="sxs-lookup"><span data-stu-id="01795-143">Filter by defined device groups.</span></span> |
| <span data-ttu-id="01795-144">Untersuchungsstatus</span><span class="sxs-lookup"><span data-stu-id="01795-144">Investigation state</span></span> | <span data-ttu-id="01795-145">Filtern von Vorfällen nach dem Status der automatisierten Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="01795-145">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="01795-146">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="01795-146">Multiple categories</span></span> | <span data-ttu-id="01795-147">Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können.</span><span class="sxs-lookup"><span data-stu-id="01795-147">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="01795-148">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="01795-148">Multiple service sources</span></span>  | <span data-ttu-id="01795-149">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="01795-149">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="01795-150">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="01795-150">OS platform</span></span> | <span data-ttu-id="01795-151">Beschränken Sie die Vorfallwarteschlange nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="01795-151">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="01795-152">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="01795-152">Service sources</span></span> | <span data-ttu-id="01795-153">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="01795-153">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="01795-154">Severity</span><span class="sxs-lookup"><span data-stu-id="01795-154">Severity</span></span> | <span data-ttu-id="01795-155">Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann.</span><span class="sxs-lookup"><span data-stu-id="01795-155">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="01795-156">Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="01795-156">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="01795-157">Status</span><span class="sxs-lookup"><span data-stu-id="01795-157">Status</span></span> | <span data-ttu-id="01795-158">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="01795-158">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="incident-response-workflow"></a><span data-ttu-id="01795-159">Workflow zur Reaktion auf Vorfälle</span><span class="sxs-lookup"><span data-stu-id="01795-159">Incident response workflow</span></span>

<span data-ttu-id="01795-160">Hier ist der typische Workflow für die Reaktion auf Vorfälle:</span><span class="sxs-lookup"><span data-stu-id="01795-160">Here is the typical workflow for responding to incidents:</span></span>

1. <span data-ttu-id="01795-161">Identifizieren und verdingen Sie die Vorfälle mit der höchsten Priorität für Untersuchung und Lösung.</span><span class="sxs-lookup"><span data-stu-id="01795-161">Identify and triage the highest priority incidents for investigation and resolution.</span></span>
2. <span data-ttu-id="01795-162">Starten Sie für jeden Vorfall mit hoher Priorität eine [Untersuchung:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="01795-162">For each high-priority incident, begin an [investigation](investigate-incidents.md):</span></span>

   <span data-ttu-id="01795-163">a.</span><span class="sxs-lookup"><span data-stu-id="01795-163">a.</span></span> <span data-ttu-id="01795-164">Zeigen Sie die Zusammenfassung des Vorfalls an, um den Umfang, die betroffenen Entitäten und den Schweregrad (die Registerkarte **Zusammenfassung) zu** verstehen.</span><span class="sxs-lookup"><span data-stu-id="01795-164">View the summary of the incident to understand it's scope, what entities are affected, and severity (the **Summary** tab).</span></span>

   <span data-ttu-id="01795-165">b.</span><span class="sxs-lookup"><span data-stu-id="01795-165">b.</span></span> <span data-ttu-id="01795-166">Schauen Sie sich die Warnungen an, um ihren Ursprung, Umfang und Schweregrad zu verstehen (registerkarte **Warnungen).**</span><span class="sxs-lookup"><span data-stu-id="01795-166">Begin looking at the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="01795-167">c.</span><span class="sxs-lookup"><span data-stu-id="01795-167">c.</span></span> <span data-ttu-id="01795-168">Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (die Registerkarten **Geräte,** **Benutzer** **und** Postfächer).</span><span class="sxs-lookup"><span data-stu-id="01795-168">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="01795-169">d.</span><span class="sxs-lookup"><span data-stu-id="01795-169">d.</span></span> <span data-ttu-id="01795-170">Erfahren Sie, wie Microsoft 365 Defender einige Warnungen automatisch aufgelöst hat (registerkarte **Untersuchungen).**</span><span class="sxs-lookup"><span data-stu-id="01795-170">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="01795-171">e.</span><span class="sxs-lookup"><span data-stu-id="01795-171">e.</span></span> <span data-ttu-id="01795-172">Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **Nachweis und** Antwort).</span><span class="sxs-lookup"><span data-stu-id="01795-172">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

<span data-ttu-id="01795-173">Bei der Untersuchung sollten Sie sich um Dies sorgen:</span><span class="sxs-lookup"><span data-stu-id="01795-173">As you investigate, you should be concerned with:</span></span>

- <span data-ttu-id="01795-174">Containment: Reduzierung zusätzlicher Auswirkungen auf Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="01795-174">Containment: Reducing any additional impact on your tenant.</span></span>
- <span data-ttu-id="01795-175">Auslöschung: Entfernen der Sicherheitsbedrohung.</span><span class="sxs-lookup"><span data-stu-id="01795-175">Eradication: Removing the security threat.</span></span>
- <span data-ttu-id="01795-176">Wiederherstellung: Wiederherstellen der Mandantenressourcen in dem Zustand, in dem sie sich vor dem Angriff auf dem Computer bew nkt haben.</span><span class="sxs-lookup"><span data-stu-id="01795-176">Recovery: Restoring your tenant resources to the state they were in before the attack.</span></span>

<span data-ttu-id="01795-177">Nachdem Sie den Vorfall behoben haben, nehmen Sie sich einen Moment Zeit, um daraus zu lernen:</span><span class="sxs-lookup"><span data-stu-id="01795-177">After you resolve the incident, take a moment to learn from it to:</span></span>

- <span data-ttu-id="01795-178">Verstehen sie den Typ des Angriffs und seine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="01795-178">Understand the type of the attack and its impact.</span></span>
- <span data-ttu-id="01795-179">Recherchieren Sie den Angriff in der Sicherheitsgemeinschaft auf einen Trend zu Sicherheitsangriffen.</span><span class="sxs-lookup"><span data-stu-id="01795-179">Research the attack in the security community for a security attack trend.</span></span>
- <span data-ttu-id="01795-180">Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre Standardworkflows und Plalbooks nach Bedarf zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="01795-180">Recall the workflow you used to resolve the incident and update your standard workflows and plalbooks as needed.</span></span>

<span data-ttu-id="01795-181">Hier finden Sie eine Zusammenfassung des grundlegenden Prozesses.</span><span class="sxs-lookup"><span data-stu-id="01795-181">Here's a summary of the basic process.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-process.png" alt-text="Grundlegendes Verfahren zur Untersuchung von Vorfällen":::

## <a name="next-step"></a><span data-ttu-id="01795-183">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="01795-183">Next step</span></span>

<span data-ttu-id="01795-184">Nachdem Sie ermittelt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus, und beginnen Sie mit der [Untersuchung.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="01795-184">After you've determined which incident requires the highest priority, select it and begin your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="01795-185">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01795-185">See also</span></span>
- [<span data-ttu-id="01795-186">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="01795-186">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="01795-187">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="01795-187">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="01795-188">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="01795-188">Manage incidents</span></span>](manage-incidents.md)

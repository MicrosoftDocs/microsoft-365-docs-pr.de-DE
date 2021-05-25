---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Informationen zum Filtern von Vorfällen aus der Vorfallwarteschlange in Microsoft 365 Defender
keywords: Incident, queue, overview, devices, identities, users, mailbox, email, incidents, analyze, response
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
ms.openlocfilehash: df2d2660267c38dccf5ef09fa4955615d3a78141
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636266"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="2e315-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e315-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="2e315-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2e315-105">**Applies to:**</span></span>
- <span data-ttu-id="2e315-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e315-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="2e315-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten in einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="2e315-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="2e315-108">Microsoft 365 Defender löst außerdem eindeutige Warnungen für Aktivitäten aus, die nur aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Produktsuite verfügt, als bösartig identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="2e315-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="2e315-109">Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsgeschichte, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="2e315-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="2e315-110">Die **Vorfallwarteschlange** zeigt eine Sammlung von Vorfällen an, die über Geräte, Benutzer und Postfächer hinweg erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2e315-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="2e315-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="2e315-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="2e315-112">Sie erhalten die Vorfallwarteschlange von **Incidents & alerts > Incidents** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="2e315-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="2e315-113">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2e315-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Warteschlange für Vorfälle":::

<span data-ttu-id="2e315-115">Der Abschnitt Neueste Vorfälle und **Warnungen** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und Vorfälle, die in den letzten 24 Stunden erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="2e315-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="2e315-116">Standardmäßig werden in der Warteschleife im Microsoft 365 Sicherheitscenter Vorfälle angezeigt, die in den letzten sechs Monaten angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="2e315-116">By default, the incident queue in the Microsoft 365 security center displays incidents seen in the last six months.</span></span> <span data-ttu-id="2e315-117">Der letzte Vorfall befindet sich ganz oben in der Liste, damit Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="2e315-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="2e315-118">Die Vorfallwarteschlange verfügt über anpassbare Spalten **(wählen** Sie Spalten auswählen) aus, die Ihnen Einblicke in verschiedene Merkmale des Vorfalls oder der betroffenen Entitäten bieten.</span><span class="sxs-lookup"><span data-stu-id="2e315-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="2e315-119">Dies hilft Ihnen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse zu treffen.</span><span class="sxs-lookup"><span data-stu-id="2e315-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="2e315-120">Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl betroffener Endpunkte, betroffener Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="2e315-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="2e315-121">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="2e315-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="2e315-122">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet wurden.*</span><span class="sxs-lookup"><span data-stu-id="2e315-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="2e315-123">Vorfälle, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="2e315-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="2e315-124">Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, mit denen Sie bei Anwendung eine umfassende Auswahl aller vorhandenen Vorfälle in Ihrer Umgebung durchführen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="2e315-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="2e315-125">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="2e315-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="2e315-126">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="2e315-126">Available filters</span></span>

<span data-ttu-id="2e315-127">In der Standardwarteschlange für Vorfälle können Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie einen gefilterten Satz von Vorfällen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="2e315-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="2e315-128">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2e315-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

<span data-ttu-id="2e315-130">In dieser Tabelle sind die verfügbaren Filternamen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2e315-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="2e315-131">Filtername</span><span class="sxs-lookup"><span data-stu-id="2e315-131">Filter name</span></span> | <span data-ttu-id="2e315-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e315-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="2e315-133">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="2e315-133">Assigned to</span></span> | <span data-ttu-id="2e315-134">Sie können Warnungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2e315-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="2e315-135">Kategorien</span><span class="sxs-lookup"><span data-stu-id="2e315-135">Categories</span></span> | <span data-ttu-id="2e315-136">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="2e315-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="2e315-137">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="2e315-137">Classification</span></span> | <span data-ttu-id="2e315-138">Filtern von Vorfällen basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="2e315-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="2e315-139">Die Werte umfassen echte Warnungen, falsche Warnungen oder nicht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2e315-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="2e315-140">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="2e315-140">Data sensitivity</span></span> | <span data-ttu-id="2e315-141">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="2e315-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="2e315-142">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="2e315-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="2e315-143">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="2e315-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="2e315-144">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="2e315-144">Device group</span></span> | <span data-ttu-id="2e315-145">Nach definierten Gerätegruppen filtern.</span><span class="sxs-lookup"><span data-stu-id="2e315-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="2e315-146">Untersuchungsstatus</span><span class="sxs-lookup"><span data-stu-id="2e315-146">Investigation state</span></span> | <span data-ttu-id="2e315-147">Filtern von Vorfällen nach dem Status der automatisierten Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="2e315-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="2e315-148">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="2e315-148">Multiple categories</span></span> | <span data-ttu-id="2e315-149">Sie können auswählen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schaden verursachen können.</span><span class="sxs-lookup"><span data-stu-id="2e315-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="2e315-150">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="2e315-150">Multiple service sources</span></span>  | <span data-ttu-id="2e315-151">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus verschiedenen Quellen enthalten (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span><span class="sxs-lookup"><span data-stu-id="2e315-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="2e315-152">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="2e315-152">OS platform</span></span> | <span data-ttu-id="2e315-153">Beschränken Sie die Vorfallwarteschlange nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="2e315-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="2e315-154">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="2e315-154">Service sources</span></span> | <span data-ttu-id="2e315-155">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e315-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="2e315-156">Severity</span><span class="sxs-lookup"><span data-stu-id="2e315-156">Severity</span></span> | <span data-ttu-id="2e315-157">Der Schweregrad eines Vorfalls ist ein Indiz für die Auswirkungen, die er auf Ihre Ressourcen haben kann.</span><span class="sxs-lookup"><span data-stu-id="2e315-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="2e315-158">Je höher der Schweregrad, desto größer sind die Auswirkungen und erfordern in der Regel die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="2e315-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="2e315-159">Status</span><span class="sxs-lookup"><span data-stu-id="2e315-159">Status</span></span> | <span data-ttu-id="2e315-160">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="2e315-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="next-steps"></a><span data-ttu-id="2e315-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2e315-161">Next steps</span></span>

<span data-ttu-id="2e315-162">Nachdem Sie ermittelt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus, und:</span><span class="sxs-lookup"><span data-stu-id="2e315-162">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="2e315-163">[Verwalten](manage-incidents.md) Sie die Eigenschaften des Vorfalls für Tags, Zuordnung, sofortige Lösung für falsch positive Vorfälle und Kommentare.</span><span class="sxs-lookup"><span data-stu-id="2e315-163">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="2e315-164">Beginnen Sie ihre [Untersuchungen](investigate-incidents.md).</span><span class="sxs-lookup"><span data-stu-id="2e315-164">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e315-165">Sehen Sie ebenfalls</span><span class="sxs-lookup"><span data-stu-id="2e315-165">See also</span></span>
- [<span data-ttu-id="2e315-166">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="2e315-166">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="2e315-167">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="2e315-167">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="2e315-168">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="2e315-168">Investigate incidents</span></span>](investigate-incidents.md)

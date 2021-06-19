---
title: Priorisieren von Vorfällen in Microsoft 365 Defender
description: Erfahren Sie, wie Sie Vorfälle aus der Vorfallwarteschlange in Microsoft 365 Defender
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
ms.openlocfilehash: 4d793d49d669510b722a72160ae396ee73ab9699
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028511"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a><span data-ttu-id="5f670-104">Priorisieren von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f670-104">Prioritize incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5f670-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5f670-105">**Applies to:**</span></span>
- <span data-ttu-id="5f670-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f670-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="5f670-107">Microsoft 365 Defender wendet Korrelationsanalysen an und aggregiert zugehörige Warnungen und automatisierte Untersuchungen aus verschiedenen Produkten zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="5f670-107">Microsoft 365 Defender applies correlation analytics and aggregates related alerts and automated investigations from different products into an incident.</span></span> <span data-ttu-id="5f670-108">Microsoft 365 Defender löst auch eindeutige Warnungen für Aktivitäten aus, die aufgrund der End-to-End-Sichtbarkeit, die Microsoft 365 Defender über die gesamte Produktsuite hat, nur als bösartig erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="5f670-108">Microsoft 365 Defender also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft 365 Defender has across the entire suite of products.</span></span> <span data-ttu-id="5f670-109">Diese Ansicht bietet Ihren Sicherheitsanalysten die umfassendere Angriffsstory, die ihnen dabei hilft, komplexe Bedrohungen in Ihrer Organisation besser zu verstehen und damit umzugehen.</span><span class="sxs-lookup"><span data-stu-id="5f670-109">This view gives your security analysts the broader attack story, which help them better understand and deal with complex threats across your organization.</span></span>

<span data-ttu-id="5f670-110">In der **Vorfallswarteschlange** wird eine Sammlung von Vorfällen angezeigt, die geräte-, benutzer- und postfachübergreifend erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f670-110">The **Incident queue** shows a collection of incidents that were created across devices, users, and mailboxes.</span></span> <span data-ttu-id="5f670-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="5f670-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span> 

<span data-ttu-id="5f670-112">Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals [(](https://security.microsoft.com)security.microsoft.com ) von **Vorfällen & Warnungen > Vorfällen** in die Vorfallswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="5f670-112">You get to the incident queue from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="5f670-113">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5f670-113">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Beispiel für die Vorfallwarteschlange":::

<span data-ttu-id="5f670-115">Der Abschnitt **"Letzte Vorfälle und Warnungen"** zeigt ein Diagramm der Anzahl der empfangenen Warnungen und vorfälle, die in den letzten 24 Stunden erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f670-115">The **Most recent incidents and alerts** section shows a graph of the number of alerts received and incidents created in the last 24 hours.</span></span>

<span data-ttu-id="5f670-116">Standardmäßig zeigt die Vorfallwarteschlange im Microsoft 365 Defender-Portal Vorfälle an, die in den letzten sechs Monaten angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="5f670-116">By default, the incident queue in the Microsoft 365 Defender portal displays incidents seen in the last six months.</span></span> <span data-ttu-id="5f670-117">Der letzte Vorfall befindet sich oben in der Liste, sodass Sie ihn zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="5f670-117">The most recent incident is at the top of the list so you can see it first.</span></span>

<span data-ttu-id="5f670-118">Die Vorfallwarteschlange verfügt über anpassbare Spalten **(Spalten** auswählen), die Ihnen Einblicke in verschiedene Merkmale des Vorfalls oder die betroffenen Entitäten bieten.</span><span class="sxs-lookup"><span data-stu-id="5f670-118">The incident queue has customizable columns (select **Choose columns**) that give you visibility into different characteristics of the incident or the impacted entities.</span></span> <span data-ttu-id="5f670-119">Auf diese Weise können Sie eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen für die Analyse treffen.</span><span class="sxs-lookup"><span data-stu-id="5f670-119">This helps you make an informed decision regarding the prioritization of incidents for analysis.</span></span>

<span data-ttu-id="5f670-120">Für eine zusätzliche Sichtbarkeit auf einen Blick generiert die automatische Vorfallbenennung Vorfallnamen basierend auf Warnungsattributen wie der Anzahl der betroffenen Endpunkte, betroffenen Benutzer, Erkennungsquellen oder Kategorien.</span><span class="sxs-lookup"><span data-stu-id="5f670-120">For additional visibility at a glance, automatic incident naming generates incident names based on alert attributes such as the number of endpoints affected, users affected, detection sources, or categories.</span></span> <span data-ttu-id="5f670-121">Auf diese Weise können Sie den Umfang des Vorfalls schnell verstehen.</span><span class="sxs-lookup"><span data-stu-id="5f670-121">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="5f670-122">Beispiel: *Mehrstufiger Vorfall auf mehreren Endpunkten, die von mehreren Quellen gemeldet werden.*</span><span class="sxs-lookup"><span data-stu-id="5f670-122">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="5f670-123">Bei Vorfällen, die vor dem Rollout der automatischen Benennung von Vorfällen vorhanden waren, wird ihr Name nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="5f670-123">Incidents that existed prior the rollout of automatic incident naming will not have their name changed.</span></span>

<span data-ttu-id="5f670-124">Die Vorfallwarteschlange macht auch mehrere Filteroptionen verfügbar, die es Ihnen bei Anwendung ermöglichen, alle vorhandenen Vorfälle in Ihrer Umgebung umfassend zu durchlaufen oder sich auf ein bestimmtes Szenario oder eine bestimmte Bedrohung zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="5f670-124">The incident queue also exposes multiple filtering options, that when applied, enable you to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="5f670-125">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5f670-125">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="5f670-126">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="5f670-126">Available filters</span></span>

<span data-ttu-id="5f670-127">In der Standardvorfallswarteschlange können Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie eine gefilterte Gruppe von Vorfällen anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="5f670-127">From the default incident queue, you can select **Filters** to see a Filters pane, from which you can view a filtered set of incidents.</span></span> <span data-ttu-id="5f670-128">Hier ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="5f670-128">Here is an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Beispiel für den Filterbereich für die Vorfallwarteschlange":::

<span data-ttu-id="5f670-130">In dieser Tabelle sind die verfügbaren Filternamen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="5f670-130">This table lists the filter names that are available.</span></span>

| <span data-ttu-id="5f670-131">Filtername</span><span class="sxs-lookup"><span data-stu-id="5f670-131">Filter name</span></span> | <span data-ttu-id="5f670-132">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f670-132">Description</span></span> |
|:-------|:-----|
| <span data-ttu-id="5f670-133">Zugewiesen an</span><span class="sxs-lookup"><span data-stu-id="5f670-133">Assigned to</span></span> | <span data-ttu-id="5f670-134">Sie können Benachrichtigungen anzeigen, die Ihnen zugewiesen sind oder die von der Automatisierung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5f670-134">You can choose to show alerts that are assigned to you or those handled by automation.</span></span> |
| <span data-ttu-id="5f670-135">Kategorien</span><span class="sxs-lookup"><span data-stu-id="5f670-135">Categories</span></span> | <span data-ttu-id="5f670-136">Wählen Sie Kategorien aus, um sich auf bestimmte Taktiken, Techniken oder Angriffskomponenten zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="5f670-136">Choose categories to focus on specific tactics, techniques, or attack components seen.</span></span> |
| <span data-ttu-id="5f670-137">Klassifizierung</span><span class="sxs-lookup"><span data-stu-id="5f670-137">Classification</span></span> | <span data-ttu-id="5f670-138">Filtern sie Vorfälle basierend auf den festgelegten Klassifizierungen der zugehörigen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="5f670-138">Filter incidents based on the set classifications of the related alerts.</span></span> <span data-ttu-id="5f670-139">Zu den Werten gehören echte, falsche oder nicht festgelegte Warnungen.</span><span class="sxs-lookup"><span data-stu-id="5f670-139">The values include true alerts, false alerts, or not set.</span></span> |
| <span data-ttu-id="5f670-140">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="5f670-140">Data sensitivity</span></span> | <span data-ttu-id="5f670-141">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="5f670-141">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="5f670-142">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="5f670-142">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span> <br><br> <span data-ttu-id="5f670-143">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5f670-143">Only applicable if Microsoft Information Protection is turned on.</span></span>|
| <span data-ttu-id="5f670-144">Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="5f670-144">Device group</span></span> | <span data-ttu-id="5f670-145">Filtern nach definierten Gerätegruppen.</span><span class="sxs-lookup"><span data-stu-id="5f670-145">Filter by defined device groups.</span></span> |
| <span data-ttu-id="5f670-146">Untersuchungsstatus</span><span class="sxs-lookup"><span data-stu-id="5f670-146">Investigation state</span></span> | <span data-ttu-id="5f670-147">Filtern sie Vorfälle nach dem Status der automatischen Untersuchung.</span><span class="sxs-lookup"><span data-stu-id="5f670-147">Filter incidents by the status of automated investigation.</span></span>  |
| <span data-ttu-id="5f670-148">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="5f670-148">Multiple categories</span></span> | <span data-ttu-id="5f670-149">Sie können festlegen, dass nur Vorfälle angezeigt werden, die mehreren Kategorien zugeordnet sind und somit potenziell mehr Schäden verursachen können.</span><span class="sxs-lookup"><span data-stu-id="5f670-149">You can choose to see only incidents that have mapped to multiple categories  and can thus potentially cause more damage.</span></span> |
| <span data-ttu-id="5f670-150">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="5f670-150">Multiple service sources</span></span>  | <span data-ttu-id="5f670-151">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus verschiedenen Quellen enthalten (Microsoft Defender für Endpunkt, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="5f670-151">Filter to only see incidents that contain alerts from different sources (Microsoft Defender for Endpoint, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365).</span></span> |
| <span data-ttu-id="5f670-152">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="5f670-152">OS platform</span></span> | <span data-ttu-id="5f670-153">Beschränken Sie die Vorfallwarteschlangenansicht nach Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="5f670-153">Limit the incident queue view by operating system.</span></span> |
| <span data-ttu-id="5f670-154">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="5f670-154">Service sources</span></span> | <span data-ttu-id="5f670-155">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="5f670-155">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> |
| <span data-ttu-id="5f670-156">Severity</span><span class="sxs-lookup"><span data-stu-id="5f670-156">Severity</span></span> | <span data-ttu-id="5f670-157">Der Schweregrad eines Vorfalls ist ein Indikator für die Auswirkungen, die er auf Ihre Ressourcen haben kann.</span><span class="sxs-lookup"><span data-stu-id="5f670-157">The severity of an incident is indicative of the impact it can have on your assets.</span></span> <span data-ttu-id="5f670-158">Je höher der Schweregrad, desto größer die Auswirkung und erfordert in der Regel die unmittelbarste Aufmerksamkeit.</span><span class="sxs-lookup"><span data-stu-id="5f670-158">The higher the severity, the bigger the impact and typically requires the most immediate attention.</span></span> |
| <span data-ttu-id="5f670-159">Status</span><span class="sxs-lookup"><span data-stu-id="5f670-159">Status</span></span> | <span data-ttu-id="5f670-160">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="5f670-160">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span> |
|||

## <a name="save-defined-filters-as-urls"></a><span data-ttu-id="5f670-161">Speichern von definierten Filtern als URLs</span><span class="sxs-lookup"><span data-stu-id="5f670-161">Save defined filters as URLs</span></span>

<span data-ttu-id="5f670-162">Nachdem Sie einen nützlichen Filter in der Vorfallwarteschlange konfiguriert haben, können Sie die URL der Browserregisterkarte mit einem Lesezeichen versehen oder auf andere Weise als Link auf einer Webseite, einem Word-Dokument oder einem Ort Ihrer Wahl speichern.</span><span class="sxs-lookup"><span data-stu-id="5f670-162">Once you have configured a useful filter in the incidents queue, you can bookmark the URL of the browser tab or otherwise save it as a link on a Web page, a Word document, or a place of your choice.</span></span> <span data-ttu-id="5f670-163">Dadurch erhalten Sie Mit-Klick-Zugriff auf wichtige Ansichten der Vorfallwarteschlange, z. B.:</span><span class="sxs-lookup"><span data-stu-id="5f670-163">This will give you single-click access to key views of the incident queue, such as:</span></span>

- <span data-ttu-id="5f670-164">Neue Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5f670-164">New incidents</span></span>
- <span data-ttu-id="5f670-165">Vorfälle mit hohem Schweregrad</span><span class="sxs-lookup"><span data-stu-id="5f670-165">High-severity incidents</span></span>
- <span data-ttu-id="5f670-166">Nicht zugewiesene Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5f670-166">Unassigned incidents</span></span>
- <span data-ttu-id="5f670-167">Vorfälle mit hohem Schweregrad, nicht zugewiesen</span><span class="sxs-lookup"><span data-stu-id="5f670-167">High-severity, unassigned incidents</span></span>
- <span data-ttu-id="5f670-168">Mir zugewiesene Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5f670-168">Incidents assigned to me</span></span>
- <span data-ttu-id="5f670-169">Mir zugewiesene Vorfälle und für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5f670-169">Incidents assigned to me and for Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="5f670-170">Vorfälle mit einem bestimmten Tag oder bestimmten Tags</span><span class="sxs-lookup"><span data-stu-id="5f670-170">Incidents with a specific tag or tags</span></span>
- <span data-ttu-id="5f670-171">Vorfälle mit einer bestimmten Bedrohungskategorie</span><span class="sxs-lookup"><span data-stu-id="5f670-171">Incidents with a specific threat category</span></span>
- <span data-ttu-id="5f670-172">Vorfälle mit einer bestimmten zugehörigen Bedrohung</span><span class="sxs-lookup"><span data-stu-id="5f670-172">Incidents with a specific associated threat</span></span>
- <span data-ttu-id="5f670-173">Vorfälle mit einem bestimmten Akteur</span><span class="sxs-lookup"><span data-stu-id="5f670-173">Incidents with a specific actor</span></span>

<span data-ttu-id="5f670-174">Nachdem Sie Ihre Liste nützlicher Filteransichten als URLs kompiliert und gespeichert haben, können Sie sie verwenden, um die Vorfälle in Ihrer Warteschlange schnell zu verarbeiten und zu priorisieren und für die nachfolgende Zuweisung und Analyse [zu verwalten.](manage-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5f670-174">Once you have compiled and stored your list of useful filter views as URLs, you can use it to quickly process and prioritize the incidents in your queue and [manage](manage-incidents.md) them for subsequent assignment and analysis.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5f670-175">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5f670-175">Next steps</span></span>

<span data-ttu-id="5f670-176">Nachdem Sie festgestellt haben, welcher Vorfall die höchste Priorität erfordert, wählen Sie ihn aus und:</span><span class="sxs-lookup"><span data-stu-id="5f670-176">After you've determined which incident requires the highest priority, select it and:</span></span>

- <span data-ttu-id="5f670-177">[Verwalten Sie](manage-incidents.md) die Eigenschaften des Vorfalls für Tags, Zuweisung, sofortige Lösung für falsch positive Vorfälle und Kommentare.</span><span class="sxs-lookup"><span data-stu-id="5f670-177">[Manage](manage-incidents.md) the properties of the incident for tags, assignment, immediate resolution for false positive incidents, and comments.</span></span>
- <span data-ttu-id="5f670-178">Beginnen Sie Ihre [Untersuchungen.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="5f670-178">Begin your [investigations](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5f670-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f670-179">See also</span></span>
- [<span data-ttu-id="5f670-180">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5f670-180">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5f670-181">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5f670-181">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="5f670-182">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5f670-182">Investigate incidents</span></span>](investigate-incidents.md)

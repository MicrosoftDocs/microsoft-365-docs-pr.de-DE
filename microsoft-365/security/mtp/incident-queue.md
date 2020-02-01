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
ms.openlocfilehash: 5ad616deb8717772a68b01147ed858f8e7f6ed7b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600252"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="e8487-104">Priorisieren von Vorfällen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e8487-104">Prioritize incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="e8487-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e8487-105">**Applies to:**</span></span>
- <span data-ttu-id="e8487-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e8487-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="e8487-107">Microsoft Threat Protection wendet Korrelationsanalysen an und fasst alle zugehörigen Warnungen und Untersuchungen aus verschiedenen Produkten in einem einzigen Vorfall zusammen.</span><span class="sxs-lookup"><span data-stu-id="e8487-107">Microsoft Threat Protection applies correlation analytics and aggregates all related alerts and investigations from different products into one incident.</span></span> <span data-ttu-id="e8487-108">Microsoft Threat Protection löst auch eindeutige Warnungen zu Aktivitäten aus, die nur aufgrund der umfassenden Transparenz von Microsoft Threat Protection über das gesamte System und die gesamte Suite von Produkten als bösartig erkannt werden können.</span><span class="sxs-lookup"><span data-stu-id="e8487-108">Microsoft Threat Protection also triggers unique alerts on activities that can only be identified as malicious given the end-to-end visibility that Microsoft Threat Protection has across the entire estate and suite of products.</span></span> <span data-ttu-id="e8487-109">Auf diese Weise kommentiert Microsoft Threat Protection die umfassendere Angriffsgeschichte, sodass ein Analyst für Sicherheitsoperationen komplexe Bedrohungen in der gesamten Organisation erkennen und bewältigen kann.</span><span class="sxs-lookup"><span data-stu-id="e8487-109">By doing so, Microsoft Threat Protection narrates the broader attack story, allowing a security operations analyst to understand and deal with complex threats across the organization.</span></span>


<span data-ttu-id="e8487-110">In der **Vorfallswarteschlange** wird eine Auflistung von Vorfällen angezeigt, die auf allen Geräten, für alle Benutzer und in allen Postfächern gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="e8487-110">The **Incidents queue** shows a collection of incidents that were flagged from across devices, users, and mailboxes.</span></span> <span data-ttu-id="e8487-111">Sie können damit Vorfälle sortieren, um eine fundierte Entscheidung im Hinblick auf eine geeignete Reaktion auf einen Cyberangriff zu treffen.</span><span class="sxs-lookup"><span data-stu-id="e8487-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>


![Abbildung einer Vorfallswarteschlange](../images/incidents-queue.png) 

<span data-ttu-id="e8487-113">Standardmäßig werden in der Warteschlange im Microsoft 365 Security Center Vorfälle angezeigt, die in den letzten 30 Tagen aufgetreten sind, wobei der letzte Vorfall am Anfang der Liste angezeigt wird, sodass Sie die neuesten Vorfälle zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="e8487-113">By default, the queue in the Microsoft 365 security center displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="e8487-114">Die Vorfallswarteschlange bietet anpassbare Spalten, die Ihnen einen Einblick in die unterschiedlichen Merkmale des Vorfalls oder in die enthaltenen Entitäten verschaffen, und Ihnen helfen, eine fundierte Entscheidung hinsichtlich der Priorisierung von Vorfällen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="e8487-114">The incident queue exposes customizable columns that give you visibility into different characteristics of the incident or the contained entities, helping you make an informed decision regarding prioritization of incidents to handle.</span></span> 

<span data-ttu-id="e8487-115">Die Vorfallswarteschlange stellt außerdem mehrere Filteroptionen zur Verfügung. Wenn diese angewendet werden, können Sie auswählen, ob Sie alle vorhandenen Vorfälle in Ihrer Umgebung umfassend aufräumen oder sich auf ein bestimmtes Szenario oder eine Bedrohung konzentrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e8487-115">The incident queue also exposes multiple filtering options, that when applied, enable you to choose to perform a broad sweep of all existing incidents in your environment, or decide to focus on a specific scenario or threat.</span></span> <span data-ttu-id="e8487-116">Durch Anwenden von Filtern in der Vorfallswarteschlange können Sie ermitteln, welcher Vorfall sofort beachtet werden muss.</span><span class="sxs-lookup"><span data-stu-id="e8487-116">Applying filters on the incident queue can help determine which incident requires immediate attention.</span></span> 

## <a name="available-filters"></a><span data-ttu-id="e8487-117">Verfügbare Filter</span><span class="sxs-lookup"><span data-stu-id="e8487-117">Available filters</span></span>

### <a name="status"></a><span data-ttu-id="e8487-118">Status</span><span class="sxs-lookup"><span data-stu-id="e8487-118">Status</span></span>
<span data-ttu-id="e8487-119">Sie können die Liste der Vorfälle basierend auf deren Status einschränken, um zu sehen, welche Vorgänge aktiv oder aufgelöst sind.</span><span class="sxs-lookup"><span data-stu-id="e8487-119">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="severity"></a><span data-ttu-id="e8487-120">Schweregrad</span><span class="sxs-lookup"><span data-stu-id="e8487-120">Severity</span></span>
<span data-ttu-id="e8487-121">Der Schweregrad eines Vorfalls ist ein Indikator für die Auswirkungen, die dieser bei Ihnen haben kann.</span><span class="sxs-lookup"><span data-stu-id="e8487-121">The severity of an incident is indicative of the impact it can have in your assets.</span></span> <span data-ttu-id="e8487-122">Je höher der Schweregrad, desto größer die Auswirkungen. In der Regel ist bei einem höheren Schweregrad auch die größte sofortige Aufmerksamkeit erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e8487-122">The higher the severity the bigger the impact and typically requires the most immediate attention.</span></span> 

### <a name="assigned-to-owner"></a><span data-ttu-id="e8487-123">Zugewiesen zu (Benutzer)</span><span class="sxs-lookup"><span data-stu-id="e8487-123">Assigned to (owner)</span></span>
<span data-ttu-id="e8487-124">Sie können die Liste filtern, indem Sie Vorfälle auswählen, die einer Person oder Ihnen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="e8487-124">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="multiple-alerts"></a><span data-ttu-id="e8487-125">Mehrere Warnungen</span><span class="sxs-lookup"><span data-stu-id="e8487-125">Multiple alerts</span></span> 
<span data-ttu-id="e8487-126">Filtern Sie, um nur Vorfälle mit mehr als einer Warnung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e8487-126">Filter to see only incidents containing more than one alert.</span></span> <span data-ttu-id="e8487-127">Dies kann ein Anzeichen für einen Angriff sein, der komplexer oder in der Kill Chain weiter fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="e8487-127">This could be an indication for an attack that is more complex or progressed in the kill chain.</span></span> 


### <a name="multiple-service-sources"></a><span data-ttu-id="e8487-128">Mehrere Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="e8487-128">Multiple service sources</span></span> 
<span data-ttu-id="e8487-129">Filtern Sie, um nur Vorfälle anzuzeigen, die Warnungen aus unterschiedlichen Quellen enthalten (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span><span class="sxs-lookup"><span data-stu-id="e8487-129">Filter to only see incidents that contain alerts from different sources (Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP)</span></span>
### <a name="service-sources"></a><span data-ttu-id="e8487-130">Dienstquellen</span><span class="sxs-lookup"><span data-stu-id="e8487-130">Service sources</span></span>
<span data-ttu-id="e8487-131">Wenn Sie eine bestimmte Quelle auswählen, können Sie sich auf Vorfälle konzentrieren, die mindestens eine Warnung aus der ausgewählten Quelle enthalten.</span><span class="sxs-lookup"><span data-stu-id="e8487-131">By choosing a specific source, you can focus on incidents that contain at least one alert from that chosen source.</span></span> 

### <a name="multiple-categories"></a><span data-ttu-id="e8487-132">Mehrere Kategorien</span><span class="sxs-lookup"><span data-stu-id="e8487-132">Multiple categories</span></span> 
<span data-ttu-id="e8487-133">Sie können auswählen, dass nur Vorfälle angezeigt werden sollen, die mehreren Kategorien der Kill Chain zugeordnet sind und möglicherweise zu weiteren Beschädigungen führen können.</span><span class="sxs-lookup"><span data-stu-id="e8487-133">You can choose to see only incidents that have mapped to multiple categories of the kill chain and can potentially cause more damage.</span></span> 

### <a name="categories"></a><span data-ttu-id="e8487-134">Kategorien</span><span class="sxs-lookup"><span data-stu-id="e8487-134">Categories</span></span>
<span data-ttu-id="e8487-135">Wählen Sie bestimmte Kategorien aus, um sich auf einen bestimmten Schritt in der Kill Chain zu konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="e8487-135">Choose specific categories to focus on a specific step in the kill chain</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="e8487-136">Vertraulichkeit der Daten</span><span class="sxs-lookup"><span data-stu-id="e8487-136">Data sensitivity</span></span>
<span data-ttu-id="e8487-137">Bei einigen Angriffen liegt der Schwerpunkt auf dem Exfiltrieren von vertraulichen oder wertvollen Daten.</span><span class="sxs-lookup"><span data-stu-id="e8487-137">Some attacks focus on targeting to exfiltrate sensitive or valuable data.</span></span> <span data-ttu-id="e8487-138">Indem Sie einen Filter anwenden, um festzustellen, ob vertrauliche Daten an dem Vorfall beteiligt sind, können Sie schnell ermitteln, ob vertrauliche Informationen potenziell gefährdet sind, und die Behebung dieser Vorfälle priorisieren.</span><span class="sxs-lookup"><span data-stu-id="e8487-138">By applying a filter to see if sensitive data is involved in the incident, you can quickly determine if sensitive information has potentially been compromised and prioritize addressing those incidents.</span></span>

>[!NOTE]
><span data-ttu-id="e8487-139">Gilt nur, wenn Microsoft Information Protection aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8487-139">Only applicable if Microsoft Information Protection is turned on.</span></span>


## <a name="next-steps"></a><span data-ttu-id="e8487-140">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e8487-140">Next steps</span></span>
<span data-ttu-id="e8487-141">Nachdem Sie festgestellt haben, für welchen Vorfall die höchste Priorität erforderlich ist, können Sie fortfahren und einen Vorfall näher untersuchen.</span><span class="sxs-lookup"><span data-stu-id="e8487-141">After you've determined which incident requires the highest priority, you can proceed to do further investigative work on an incident.</span></span>
- [<span data-ttu-id="e8487-142">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="e8487-142">Investigate incidents</span></span>](investigate-incidents.md)


## <a name="related-topics"></a><span data-ttu-id="e8487-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="e8487-143">Related topics</span></span>
- [<span data-ttu-id="e8487-144">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="e8487-144">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="e8487-145">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="e8487-145">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="e8487-146">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="e8487-146">Manage incidents</span></span>](manage-incidents.md)
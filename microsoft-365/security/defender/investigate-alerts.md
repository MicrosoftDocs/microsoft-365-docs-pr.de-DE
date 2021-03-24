---
title: Untersuchen von Warnungen in Microsoft 365 Defender
description: Untersuchen Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
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
ms.openlocfilehash: bc325f88ec41861c2adc4d5147e94d2d2d5b1ebe
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060755"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="5ac91-104">Untersuchen von Warnungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ac91-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5ac91-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5ac91-105">**Applies to:**</span></span>
- <span data-ttu-id="5ac91-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ac91-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="5ac91-107">Warnungen sind die Grundlage aller Vorfälle und geben das Auftreten von böswilligen oder verdächtigen Ereignissen in Ihrer Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="5ac91-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="5ac91-108">Warnungen sind in der Regel Teil eines umfassenderen Angriffs und liefern Hinweise zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="5ac91-108">Alerts are typically part of a broader attack and provide pieces of clues about an incident.</span></span>

<span data-ttu-id="5ac91-109">In Microsoft 365 Defender werden verwandte Warnungen zu Vorfällen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="5ac91-109">In Microsoft 365 Defender, related alerts are aggregated together to form incidents.</span></span> <span data-ttu-id="5ac91-110">Vorfälle bieten immer den umfassenderen Kontext eines Angriffs. Es kann jedoch hilfreich sein, Warnungen zu untersuchen, wenn eine tiefergehende Analyse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5ac91-110">Incidents will always provide the broader context of an attack, however, investigating alerts can be valuable when deeper analysis is required.</span></span> 



## <a name="using-alert-pages-in-investigations"></a><span data-ttu-id="5ac91-111">Verwenden von Warnungsseiten in Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="5ac91-111">Using alert pages in investigations</span></span>

<span data-ttu-id="5ac91-112">Auf der Registerkarte Warnungen auf jeder Vorfallseite gelangen Sie durch Auswählen einer Warnung zu den einzelnen Warnungsseiten.</span><span class="sxs-lookup"><span data-stu-id="5ac91-112">From the Alerts tab of any incident page, selecting an alert brings you to the individual alert pages.</span></span> <span data-ttu-id="5ac91-113">Eine Warnungsseite besteht aus drei Abschnitten: betroffenen Ressourcen, Warnungsabschnitt und Detailbereich.</span><span class="sxs-lookup"><span data-stu-id="5ac91-113">An alert page is composed of three sections: affected assets, alert story, and the details pane.</span></span>

![Abbildung der Beispielbenachrichtigungsseite](../../media/new-alert-page2.png)

<span data-ttu-id="5ac91-115">Auf einer Warnungsseite können Sie das Symbol mit drei Punkten (**...**) neben jeder Entität auswählen, damit Sie verfügbare Aktionen wie das Öffnen der bestimmten Objektseite oder bestimmte Korrekturschritte sehen können.</span><span class="sxs-lookup"><span data-stu-id="5ac91-115">Throughout an alert page, you can select the three-dot icon (**...**) beside any entity so you can see available actions like opening the specific asset page or doing specific remediation steps.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="5ac91-116">Analysieren betroffener Objekte</span><span class="sxs-lookup"><span data-stu-id="5ac91-116">Analyze affected assets</span></span>
<span data-ttu-id="5ac91-117">Im Abschnitt betroffene Objekte werden Postfächer, Geräte und Benutzer aufgeführt, die von dieser Warnung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="5ac91-117">The affected assets section lists mailboxes, devices, and users affected by this alert.</span></span> <span data-ttu-id="5ac91-118">Wenn Sie eine der Objektkarten auswählen, wird der Detailseitenbereich mit Informationen auffüllt, einschließlich anderer Warnungen, die im Zusammenhang mit den Ressourcen aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="5ac91-118">Selecting any of the asset cards populates the details side pane with information, including other alerts that occurred involving the assets, if any.</span></span>


### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="5ac91-119">Verfolgen der Rolle einer Warnung im Warnungsstory</span><span class="sxs-lookup"><span data-stu-id="5ac91-119">Trace an alert's role in the alert story</span></span>
<span data-ttu-id="5ac91-120">Der Warnungsstory zeigt alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht an.</span><span class="sxs-lookup"><span data-stu-id="5ac91-120">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="5ac91-121">Die Warnung im Titel ist die Warnung, die beim ersten Landen auf der Seite der ausgewählten Warnung im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="5ac91-121">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="5ac91-122">Objekte im Warnungsstory können erweitert und angeklickt werden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-122">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="5ac91-123">Sie bieten zusätzliche Informationen und beschleunigen die Reaktion, indem Sie Aktionen direkt im Kontext der Warnungsseite ausführen können.</span><span class="sxs-lookup"><span data-stu-id="5ac91-123">They provide additional information and expedite response by allowing you to take actions right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="5ac91-124">Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, und zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur werden vor oder nach der ausgewählten Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ac91-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-in-the-details-pane"></a><span data-ttu-id="5ac91-125">Weitere Benachrichtigungsinformationen im Detailbereich anzeigen</span><span class="sxs-lookup"><span data-stu-id="5ac91-125">View more alert information in the details pane</span></span>

<span data-ttu-id="5ac91-126">Im Detailbereich werden zunächst die Details der ausgewählten Warnung mit Details und Aktionen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ac91-126">The details pane shows the details of the selected alert at first, with details and actions related to it.</span></span> <span data-ttu-id="5ac91-127">Wenn Sie eine der betroffenen Objekte oder Entitäten im Warnungsstory auswählen, wird der Detailbereich geändert, um kontextbezogene Informationen und Aktionen für das ausgewählte Objekt zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="5ac91-127">If you select any of the affected assets or entities in the alert story, the details pane changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="5ac91-128">Nachdem Sie eine entität von Interesse ausgewählt haben, ändert sich der Detailbereich so, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, sobald diese verfügbar ist, und Optionen zum Ergreifen von Aktionen für diese Entität direkt auf der Warnungsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-128">Once you've selected an entity of interest, the details pane changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

### <a name="manage-alerts"></a><span data-ttu-id="5ac91-129">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="5ac91-129">Manage alerts</span></span>

<span data-ttu-id="5ac91-130">Nachdem Sie die Untersuchung der Warnungen durchgeführt haben, können Sie zurück zu der Benachrichtigung, mit der Sie begonnen haben, den Status der Warnung als Aufgelöst markieren und als False- oder True-Warnung klassifizieren.</span><span class="sxs-lookup"><span data-stu-id="5ac91-130">Once you're done investigating the alerts, you can go back to the alert you started with, mark the alert's status as Resolved and classify it as either a False alert or True alert.</span></span> <span data-ttu-id="5ac91-131">Das Klassifizieren von Warnungen trägt dazu bei, Ihr Produkt so zu optimieren, dass mehr echte Warnungen und weniger falsche Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-131">Classifying alerts helps tune your product to provide more true alerts and less false alerts.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac91-132">Eine Möglichkeit zum Verwalten von Warnungen mithilfe von Tags.</span><span class="sxs-lookup"><span data-stu-id="5ac91-132">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="5ac91-133">Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell ausgeführt und befindet sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="5ac91-133">The tagging capability for Microsoft Defender for Office 365 in incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="5ac91-134">Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die nach *dem Update* erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-134">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="5ac91-135">Warnungen, die vor der Änderung generiert wurden, spiegeln nicht den aktualisierten Tagnamen wider.</span><span class="sxs-lookup"><span data-stu-id="5ac91-135">Alerts that were generated prior to the modification will not reflect the updated tag name.</span></span> 


## <a name="manage-the-unified-alert-queue"></a><span data-ttu-id="5ac91-136">Verwalten der einheitlichen Warnungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="5ac91-136">Manage the unified alert queue</span></span>

<span data-ttu-id="5ac91-137">Durch Auswählen von Warnungen & Warnungen im Navigationsbereich des Microsoft 365 Security Center werden Sie zur einheitlichen Warnungswarteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ac91-137">Selecting Alerts under Incidents & Alerts in the Microsoft 365 security center navigation pane brings you to the unified alert queue.</span></span> <span data-ttu-id="5ac91-138">Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender for Endpoint, Microsoft Defender für Office 365 und Microsoft 365 Defender werden in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ac91-138">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear in this section.</span></span> 

![Abbildung der Beispielwarnungsseite](../../media/unified-alert-queue.png)

<span data-ttu-id="5ac91-140">Die Warnungswarteschlange zeigt eine Liste der Warnungen an, die in Ihrem Netzwerk gekennzeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-140">The Alerts queue shows a list of alerts that were flagged in your network.</span></span> <span data-ttu-id="5ac91-141">Standardmäßig werden in der Warteschlange Warnungen angezeigt, die in den letzten 30 Tagen angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="5ac91-141">By default, the queue displays alerts seen in the last 30 days.</span></span> <span data-ttu-id="5ac91-142">Die neuesten Warnungen werden am Anfang der Liste angezeigt, damit Sie zuerst die neuesten Warnungen sehen können.</span><span class="sxs-lookup"><span data-stu-id="5ac91-142">The most recent alerts are shown at the top of the list helping you see the most recent alerts first.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac91-143">Zum Zeitpunkt des Startes ist die Warteschlange für einheitliche Warnungen nur für 7 Tage mit Microsoft Defender für Office 365-Warnungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5ac91-143">At the time of launch, the unified alerts queue will only have 7 days’ worth of Microsoft Defender for Office 365 alerts available.</span></span> <span data-ttu-id="5ac91-144">Die Warteschlange wird im Laufe der Zeit weiter aufbaut.</span><span class="sxs-lookup"><span data-stu-id="5ac91-144">The queue will continue to build over time.</span></span> <span data-ttu-id="5ac91-145">Wenn Sie Warnungen vor dem Start der einheitlichen Benachrichtigungswarteschlange triagen müssen, verwenden Sie die Benachrichtigungswarteschlange im [Security and Compliance Center](https://protection.office.com/viewalerts).</span><span class="sxs-lookup"><span data-stu-id="5ac91-145">If you need to triage alerts prior to the launch of the unified alerts queue, use the alerts queue in the [Security and Compliance Center](https://protection.office.com/viewalerts).</span></span>


<span data-ttu-id="5ac91-146">Im oberen Navigationsbereich können Sie:</span><span class="sxs-lookup"><span data-stu-id="5ac91-146">On the top navigation, you can:</span></span>

- <span data-ttu-id="5ac91-147">Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="5ac91-147">Apply filters</span></span>
- <span data-ttu-id="5ac91-148">Anpassen von Spalten zum Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="5ac91-148">Customize columns to add or remove columns</span></span>
- <span data-ttu-id="5ac91-149">Exportieren von Daten</span><span class="sxs-lookup"><span data-stu-id="5ac91-149">Export data</span></span>

<span data-ttu-id="5ac91-150">Sie können Warnungen auch nach unterschiedlichen Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="5ac91-150">You can also filter alerts according to different criteria:</span></span>

- <span data-ttu-id="5ac91-151">Severity</span><span class="sxs-lookup"><span data-stu-id="5ac91-151">Severity</span></span>
- <span data-ttu-id="5ac91-152">Status</span><span class="sxs-lookup"><span data-stu-id="5ac91-152">Status</span></span>
- <span data-ttu-id="5ac91-153">Kategorie</span><span class="sxs-lookup"><span data-stu-id="5ac91-153">Category</span></span>
- <span data-ttu-id="5ac91-154">Erkennungsquelle</span><span class="sxs-lookup"><span data-stu-id="5ac91-154">Detection source</span></span>
- <span data-ttu-id="5ac91-155">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="5ac91-155">Policy</span></span>
- <span data-ttu-id="5ac91-156">Auswirkungen auf Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5ac91-156">Impacted assets</span></span>
- <span data-ttu-id="5ac91-157">Erste Aktivität</span><span class="sxs-lookup"><span data-stu-id="5ac91-157">First activity</span></span>
- <span data-ttu-id="5ac91-158">Letzte Aktivität</span><span class="sxs-lookup"><span data-stu-id="5ac91-158">Last activity</span></span>


<span data-ttu-id="5ac91-159">Lesen Sie Untersuchen von Vorfällen [in Microsoft 365 Defender,](investigate-incidents.md) um eine Untersuchung zu einem Vorfall zu starten.</span><span class="sxs-lookup"><span data-stu-id="5ac91-159">To start an investigation on an incident, read [Investigate incidents in Microsoft 365 Defender](investigate-incidents.md)</span></span>
## <a name="see-also"></a><span data-ttu-id="5ac91-160">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ac91-160">See also</span></span>

- [<span data-ttu-id="5ac91-161">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="5ac91-161">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="5ac91-162">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5ac91-162">Investigate incidents</span></span>](investigate-incidents.md)
- [<span data-ttu-id="5ac91-163">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="5ac91-163">Manage incidents</span></span>](manage-incidents.md)

---
title: Untersuchen von Warnungen in Microsoft 365 Defender
description: Untersuchen Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reaktion, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365
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
ms.openlocfilehash: 6a34269c414f59d40c9160d5728159ed9cddf976
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651349"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="6d53c-104">Untersuchen von Warnungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d53c-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="6d53c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6d53c-105">**Applies to:**</span></span>
- <span data-ttu-id="6d53c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d53c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="6d53c-107">Warnungen sind die Grundlage aller Vorfälle und geben das Auftreten von böswilligen oder verdächtigen Ereignissen in Ihrer Umgebung an.</span><span class="sxs-lookup"><span data-stu-id="6d53c-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="6d53c-108">Warnungen sind in der Regel Teil eines umfassenderen Angriffs und geben Hinweise zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="6d53c-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="6d53c-109">In Microsoft 365 Defender werden zugehörige Warnungen zu Vorfällen [zusammengefasst.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6d53c-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="6d53c-110">Vorfälle bieten immer den umfassenderen Kontext eines Angriffs. Die Analyse von Warnungen kann jedoch hilfreich sein, wenn eine tiefergehende Analyse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6d53c-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="6d53c-111">Die **Warnungswarteschlange** zeigt den aktuellen Satz von Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="6d53c-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="6d53c-112">Sie erhalten die Benachrichtigungswarteschlange von **Incidents & alerts > Alerts** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="6d53c-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Beispiel für die Benachrichtigungswarteschlange":::

<span data-ttu-id="6d53c-114">Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender for Endpoint, Microsoft Defender für Office 365 und Microsoft 365 Defender werden hier angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d53c-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="6d53c-115">Standardmäßig werden in der Benachrichtigungswarteschlange im Microsoft 365 die neuen und in Bearbeitung benachrichtigungen aus den letzten 30 Tagen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d53c-115">By default, the alerts queue in the Microsoft 365 security center displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="6d53c-116">Die letzte Warnung befindet sich am Anfang der Liste, damit Sie sie zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="6d53c-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="6d53c-117">In der Standardbenachrichtigungswarteschlange können  Sie **Filter** auswählen, um einen Filterbereich anzuzeigen, aus dem Sie eine Teilmenge der Warnungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="6d53c-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="6d53c-118">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6d53c-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Beispiel für den Filterbereich für die Benachrichtigungswarteschlange":::

<span data-ttu-id="6d53c-120">Sie können Warnungen nach folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="6d53c-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="6d53c-121">Severity</span><span class="sxs-lookup"><span data-stu-id="6d53c-121">Severity</span></span>
- <span data-ttu-id="6d53c-122">Status</span><span class="sxs-lookup"><span data-stu-id="6d53c-122">Status</span></span>
- <span data-ttu-id="6d53c-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6d53c-123">Category</span></span>
- <span data-ttu-id="6d53c-124">Erkennungsquelle</span><span class="sxs-lookup"><span data-stu-id="6d53c-124">Detection source</span></span>
- <span data-ttu-id="6d53c-125">Tags</span><span class="sxs-lookup"><span data-stu-id="6d53c-125">Tags</span></span>
- <span data-ttu-id="6d53c-126">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="6d53c-126">Policy</span></span>
- <span data-ttu-id="6d53c-127">Auswirkungen auf Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6d53c-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="6d53c-128">Analysieren einer Warnung</span><span class="sxs-lookup"><span data-stu-id="6d53c-128">Analyze an alert</span></span>

<span data-ttu-id="6d53c-129">Um die Hauptbenachrichtigungsseite zu sehen, wählen Sie den Namen der Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="6d53c-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="6d53c-130">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6d53c-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Security Center":::

<span data-ttu-id="6d53c-132">Sie können auch die Aktion **Hauptbenachrichtigungsseite öffnen** im Bereich **Warnung verwalten** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6d53c-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="6d53c-133">Eine Warnungsseite besteht aus den folgenden Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="6d53c-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="6d53c-134">Warnungsgeschichte, bei der es sich um die Kette von Ereignissen und Warnungen im Zusammenhang mit dieser Warnung in chronologischer Reihenfolge handelt</span><span class="sxs-lookup"><span data-stu-id="6d53c-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="6d53c-135">Zusammenfassungsdetails</span><span class="sxs-lookup"><span data-stu-id="6d53c-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Security Center":::

<span data-ttu-id="6d53c-137">Auf einer Warnungsseite können Sie neben jeder Entität die Ellipsen (**...**) auswählen, um verfügbare Aktionen zu sehen, z. B. das Öffnen der Warnungsseite oder das Verknüpfen der Warnung mit einem anderen Vorfall.</span><span class="sxs-lookup"><span data-stu-id="6d53c-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="analyze-affected-assets"></a><span data-ttu-id="6d53c-138">Analysieren betroffener Objekte</span><span class="sxs-lookup"><span data-stu-id="6d53c-138">Analyze affected assets</span></span>

<span data-ttu-id="6d53c-139">Der **Abschnitt "Aktionen"** enthält eine Liste der betroffenen Objekte, z. B. Postfächer, Geräte und Benutzer, die von dieser Warnung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="6d53c-139">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="6d53c-140">Sie können auch Ansicht **im Aktionscenter auswählen,** um die Registerkarte **Verlauf** des **Aktionscenters** im Microsoft 365 anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6d53c-140">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 security center.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="6d53c-141">Verfolgen der Rolle einer Warnung im Warnungsstory</span><span class="sxs-lookup"><span data-stu-id="6d53c-141">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="6d53c-142">Der Warnungsstory zeigt alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht an.</span><span class="sxs-lookup"><span data-stu-id="6d53c-142">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="6d53c-143">Die Warnung im Titel ist die Warnung, die beim ersten Landen auf der Seite der ausgewählten Warnung im Fokus steht.</span><span class="sxs-lookup"><span data-stu-id="6d53c-143">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="6d53c-144">Objekte im Warnungsstory können erweitert und angeklickt werden.</span><span class="sxs-lookup"><span data-stu-id="6d53c-144">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="6d53c-145">Sie stellen zusätzliche Informationen zur Verfügung und beschleunigen Ihre Antwort, indem Sie direkt im Kontext der Warnungsseite Maßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="6d53c-145">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="6d53c-146">Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, und zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur werden vor oder nach der ausgewählten Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d53c-146">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="6d53c-147">Weitere Benachrichtigungsinformationen auf der Detailseite anzeigen</span><span class="sxs-lookup"><span data-stu-id="6d53c-147">View more alert information on the details page</span></span>

<span data-ttu-id="6d53c-148">Die Detailseite zeigt die Details der ausgewählten Warnung mit Details und Aktionen im Zusammenhang mit dieser Warnung.</span><span class="sxs-lookup"><span data-stu-id="6d53c-148">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="6d53c-149">Wenn Sie eine der betroffenen Objekte oder Entitäten im Warnungsstory auswählen, wird die Detailseite geändert, um kontextbezogene Informationen und Aktionen für das ausgewählte Objekt zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="6d53c-149">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="6d53c-150">Nachdem Sie eine entität von Interesse ausgewählt haben, ändert sich die Detailseite so, dass Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn sie verfügbar ist, und Optionen zum Ergreifen von Aktionen für diese Entität direkt auf der Warnungsseite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d53c-150">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="6d53c-151">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="6d53c-151">Manage alerts</span></span>

<span data-ttu-id="6d53c-152">Um eine Warnung zu verwalten, wählen Sie die Warnung in der Benachrichtigungswarteschlange in der Zeile aus, um einen **Warnungsbereich verwalten anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="6d53c-152">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="6d53c-153">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6d53c-153">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Beispiel für den Zusammenfassungsbereich für eine Warnung":::

<span data-ttu-id="6d53c-155">Im **Bereich Warnung verwalten** können Sie:</span><span class="sxs-lookup"><span data-stu-id="6d53c-155">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="6d53c-156">Der Warnungsstatus (Neu, Aufgelöst, In Bearbeitung).</span><span class="sxs-lookup"><span data-stu-id="6d53c-156">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="6d53c-157">Die Klassifizierung der Warnung (Nicht festgelegt, True Alert, False Alert).</span><span class="sxs-lookup"><span data-stu-id="6d53c-157">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="6d53c-158">Für die Klassifizierung als echte Warnung ist der Typ der Bedrohung für die Warnung im **Feld Bestimmung.**</span><span class="sxs-lookup"><span data-stu-id="6d53c-158">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="6d53c-159">Ein Kommentar zur Warnung.</span><span class="sxs-lookup"><span data-stu-id="6d53c-159">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="6d53c-160">Eine Möglichkeit zum Verwalten von Warnungen mithilfe von Tags.</span><span class="sxs-lookup"><span data-stu-id="6d53c-160">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="6d53c-161">Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell ausgeführt und befindet sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="6d53c-161">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="6d53c-162">Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die nach *dem Update* erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="6d53c-162">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="6d53c-163">Warnungen, die vor der Änderung generiert wurden, geben nicht den aktualisierten Tagnamen wieder.</span><span class="sxs-lookup"><span data-stu-id="6d53c-163">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="6d53c-164">In diesem Bereich können Sie auch die folgenden zusätzlichen Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6d53c-164">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="6d53c-165">Öffnen der Hauptbenachrichtigungsseite</span><span class="sxs-lookup"><span data-stu-id="6d53c-165">Open the main alert page</span></span>
- <span data-ttu-id="6d53c-166">Konsultieren eines Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="6d53c-166">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="6d53c-167">Anzeigen der Übermittlung</span><span class="sxs-lookup"><span data-stu-id="6d53c-167">View submission</span></span>
- <span data-ttu-id="6d53c-168">Link zu einem anderen Vorfall</span><span class="sxs-lookup"><span data-stu-id="6d53c-168">Link to another incident</span></span>
- <span data-ttu-id="6d53c-169">Anzeigen der Warnung in einer Zeitachse</span><span class="sxs-lookup"><span data-stu-id="6d53c-169">See the alert in a timeline</span></span>
- <span data-ttu-id="6d53c-170">Erstellen einer Unterdrückungsregel</span><span class="sxs-lookup"><span data-stu-id="6d53c-170">Create a suppression rule</span></span>

<span data-ttu-id="6d53c-171">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="6d53c-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Beispiel für die Aktionen für eine Warnung im Microsoft 365 Security Center":::

<span data-ttu-id="6d53c-173">Die Liste der zusätzlichen Aktionen hängt vom Typ der Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="6d53c-173">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="6d53c-174">Auflösen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="6d53c-174">Resolve an alert</span></span>

<span data-ttu-id="6d53c-175">Sobald Sie die Analyse einer Warnung durchgeführt haben und  diese aufgelöst werden kann, wechseln Sie zum Bereich Warnung verwalten  für die Warnung, markieren Sie den Status als **Aufgelöst,** und klassifizieren Sie sie entweder als False-Warnung oder **als True-Warnung.**</span><span class="sxs-lookup"><span data-stu-id="6d53c-175">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="6d53c-176">Geben Sie bei echten Warnungen den Bedrohungstyp der Warnung im Feld **Bestimmung** an.</span><span class="sxs-lookup"><span data-stu-id="6d53c-176">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="6d53c-177">Das Klassifizieren von Warnungen und das Angeben ihrer Bestimmung trägt dazu bei, Microsoft 365 Defender so zu optimieren, dass mehr echte Warnungen und weniger falsch Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6d53c-177">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6d53c-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6d53c-178">Next steps</span></span>

<span data-ttu-id="6d53c-179">Setzen Sie ihre Untersuchung nach Bedarf für Prozessvorfälle [fort.](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="6d53c-179">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="6d53c-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d53c-180">See also</span></span>

- [<span data-ttu-id="6d53c-181">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="6d53c-181">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="6d53c-182">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6d53c-182">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="6d53c-183">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6d53c-183">Investigate incidents</span></span>](investigate-incidents.md)

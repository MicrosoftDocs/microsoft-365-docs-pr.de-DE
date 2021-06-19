---
title: Untersuchen von Warnungen in Microsoft 365 Defender
description: Untersuchen Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reagieren, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
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
ms.openlocfilehash: 567916e9e1a1d96d77bc6c187b384a1ec3be72a5
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022708"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a><span data-ttu-id="72607-104">Untersuchen von Warnungen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72607-104">Investigate alerts in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="72607-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="72607-105">**Applies to:**</span></span>
- <span data-ttu-id="72607-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="72607-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="72607-107">Warnungen sind die Basis aller Vorfälle und weisen auf das Auftreten bösartiger oder verdächtiger Ereignisse in Ihrer Umgebung hin.</span><span class="sxs-lookup"><span data-stu-id="72607-107">Alerts are the basis of all incidents and indicate the occurrence of malicious or suspicious events in your environment.</span></span> <span data-ttu-id="72607-108">Warnungen sind in der Regel Teil eines umfassenderen Angriffs und liefern Hinweise zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="72607-108">Alerts are typically part of a broader attack and provide clues about an incident.</span></span>

<span data-ttu-id="72607-109">In Microsoft 365 Defender werden zugehörige Warnungen zu [Vorfällen](incidents-overview.md)zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="72607-109">In Microsoft 365 Defender, related alerts are aggregated together to form [incidents](incidents-overview.md).</span></span> <span data-ttu-id="72607-110">Vorfälle bieten immer den umfassenderen Kontext eines Angriffs, die Analyse von Warnungen kann jedoch hilfreich sein, wenn eine ausführlichere Analyse erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="72607-110">Incidents will always provide the broader context of an attack, however, analyzing alerts can be valuable when deeper analysis is required.</span></span> 

<span data-ttu-id="72607-111">Die **Warnungswarteschlange** zeigt den aktuellen Satz von Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="72607-111">The **Alerts queue** shows the current set of alerts.</span></span> <span data-ttu-id="72607-112">Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals ( security.microsoft.com ) von **Vorfällen & Warnungen > Warnungen** in die Warnungswarteschlange.[](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="72607-112">You get to the alerts queue from **Incidents & alerts > Alerts** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Beispiel für die Warnungswarteschlange":::

<span data-ttu-id="72607-114">Hier werden Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender für Endpunkt, Microsoft Defender für Office 365 und Microsoft 365 Defender angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72607-114">Alerts from different Microsoft security solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft 365 Defender appear here.</span></span>

<span data-ttu-id="72607-115">Standardmäßig zeigt die Warnungswarteschlange im Microsoft 365 Defender-Portal die neuen und laufenden Warnungen der letzten 30 Tage an.</span><span class="sxs-lookup"><span data-stu-id="72607-115">By default, the alerts queue in the Microsoft 365 Defender portal displays the new and in progress alerts from the last 30 days.</span></span> <span data-ttu-id="72607-116">Die letzte Warnung befindet sich oben in der Liste, sodass Sie sie zuerst sehen können.</span><span class="sxs-lookup"><span data-stu-id="72607-116">The most recent alert is at the top of the list so you can see it first.</span></span> 

<span data-ttu-id="72607-117">In der Standardbenachrichtigungswarteschlange können Sie **Filter** auswählen, um einen **Filterbereich** anzuzeigen, aus dem Sie eine Teilmenge der Warnungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="72607-117">From the default alerts queue, you can select **Filters** to see a **Filters** pane, from which you can specify a subset of the alerts.</span></span> <span data-ttu-id="72607-118">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72607-118">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Beispiel für den Filterbereich für die Warnungswarteschlange":::

<span data-ttu-id="72607-120">Sie können Warnungen nach folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="72607-120">You can filter alerts according to these criteria:</span></span>

- <span data-ttu-id="72607-121">Severity</span><span class="sxs-lookup"><span data-stu-id="72607-121">Severity</span></span>
- <span data-ttu-id="72607-122">Status</span><span class="sxs-lookup"><span data-stu-id="72607-122">Status</span></span>
- <span data-ttu-id="72607-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="72607-123">Category</span></span>
- <span data-ttu-id="72607-124">Erkennungsquelle</span><span class="sxs-lookup"><span data-stu-id="72607-124">Detection source</span></span>
- <span data-ttu-id="72607-125">Tags</span><span class="sxs-lookup"><span data-stu-id="72607-125">Tags</span></span>
- <span data-ttu-id="72607-126">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="72607-126">Policy</span></span>
- <span data-ttu-id="72607-127">Betroffene Ressourcen</span><span class="sxs-lookup"><span data-stu-id="72607-127">Impacted assets</span></span>

## <a name="analyze-an-alert"></a><span data-ttu-id="72607-128">Analysieren einer Warnung</span><span class="sxs-lookup"><span data-stu-id="72607-128">Analyze an alert</span></span>

<span data-ttu-id="72607-129">Um die Hauptwarnungsseite anzuzeigen, wählen Sie den Namen der Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="72607-129">To see the main alert page, select the name of the alert.</span></span> <span data-ttu-id="72607-130">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72607-130">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Defender Portal":::

<span data-ttu-id="72607-132">Sie können auch die Aktion **"Hauptwarnungsseite öffnen"** im **Warnungsbereich "Verwalten"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="72607-132">You can also select the **Open the main alert page** action from the **Manage alert** pane.</span></span>

<span data-ttu-id="72607-133">Eine Warnungsseite besteht aus folgenden Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="72607-133">An alert page is composed of these sections:</span></span> 

- <span data-ttu-id="72607-134">Warnungsartikel, bei dem es sich um die Kette von Ereignissen und Warnungen im Zusammenhang mit dieser Warnung in chronologischer Reihenfolge handelt</span><span class="sxs-lookup"><span data-stu-id="72607-134">Alert story, which is the chain of events and alerts related to this alert in chronological order</span></span>
- <span data-ttu-id="72607-135">Zusammenfassungsdetails</span><span class="sxs-lookup"><span data-stu-id="72607-135">Summary details</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Defender Portal":::

<span data-ttu-id="72607-137">Auf einer Warnungsseite können Sie die Ellipsen (**...**) neben einer beliebigen Entität auswählen, um verfügbare Aktionen anzuzeigen, z. B. das Öffnen der Warnungsseite oder das Verknüpfen der Warnung mit einem anderen Vorfall.</span><span class="sxs-lookup"><span data-stu-id="72607-137">Throughout an alert page, you can select the ellipses (**...**) beside any entity to see available actions, such as opening the alert page or linking the alert to another incident.</span></span>

### <a name="alert-sources"></a><span data-ttu-id="72607-138">Warnungsquellen</span><span class="sxs-lookup"><span data-stu-id="72607-138">Alert sources</span></span>
<span data-ttu-id="72607-139">Microsoft 365 Defender Warnungen können von Lösungen wie Microsoft Defender für Endpunkt, Microsoft Defender für Office 365 und Microsoft Cloud App Security stammen.</span><span class="sxs-lookup"><span data-stu-id="72607-139">Microsoft 365 Defender alerts may come from solutions like Microsoft Defender for Endpoint, Microsoft Defender for Office 365, and Microsoft Cloud App Security.</span></span> <span data-ttu-id="72607-140">Möglicherweise werden Warnungen mit vorangestellten Zeichen in der Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72607-140">You may notice alerts with prepended characters in the alert.</span></span> <span data-ttu-id="72607-141">Die folgende Tabelle enthält Anleitungen, die Ihnen dabei helfen, die Zuordnung von Warnungsquellen basierend auf dem vorangestellten Zeichen der Warnung zu verstehen.</span><span class="sxs-lookup"><span data-stu-id="72607-141">The following table provides guidance to help you understand the mapping of alert sources based on the prepended character on the alert.</span></span>

> [!NOTE]
> - <span data-ttu-id="72607-142">Die vorangestellten GUIDs sind nur für einheitliche Umgebungen wie einheitliche Warnungswarteschlange, Seite für einheitliche Warnungen, einheitliche Untersuchung und einheitliche Vorfälle spezifisch.</span><span class="sxs-lookup"><span data-stu-id="72607-142">The prepended GUIDs are specific only to unified experiences such as unified alerts queue, unified alerts page, unified investigation, and unified incident.</span></span><br>
> - <span data-ttu-id="72607-143">Das vorangestellte Zeichen ändert nicht die GUID der Warnung.</span><span class="sxs-lookup"><span data-stu-id="72607-143">The prepended character does not change the GUID of the alert.</span></span> <span data-ttu-id="72607-144">Die einzige Änderung an der GUID ist die vorangestellte Komponente.</span><span class="sxs-lookup"><span data-stu-id="72607-144">The only change to the GUID is the prepended component.</span></span><br>


<span data-ttu-id="72607-145">Warnungsquelle</span><span class="sxs-lookup"><span data-stu-id="72607-145">Alert source</span></span> | <span data-ttu-id="72607-146">Vorangestelltes Zeichen</span><span class="sxs-lookup"><span data-stu-id="72607-146">Prepended character</span></span> 
:---|:---
<span data-ttu-id="72607-147">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="72607-147">Microsoft Defender for Office 365</span></span> | `fa{GUID}` <br> <span data-ttu-id="72607-148">Beispiel: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="72607-148">Example: `fa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="72607-149">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="72607-149">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="72607-150">`da` oder `ed` für benutzerdefinierte Erkennungswarnungen</span><span class="sxs-lookup"><span data-stu-id="72607-150">`da` or `ed` for custom detection alerts</span></span> <br> 
<span data-ttu-id="72607-151">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="72607-151">Microsoft Defender for Identity</span></span> | `aa{GUID}` <br> <span data-ttu-id="72607-152">Beispiel: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="72607-152">Example: `aa123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 
<span data-ttu-id="72607-153">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="72607-153">Microsoft Cloud App Security</span></span> |`ca{GUID}` <br> <span data-ttu-id="72607-154">Beispiel: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span><span class="sxs-lookup"><span data-stu-id="72607-154">Example: `ca123a456b-c789-1d2e-12f1g33h445h6i`</span></span> 

### <a name="analyze-affected-assets"></a><span data-ttu-id="72607-155">Analysieren betroffener Ressourcen</span><span class="sxs-lookup"><span data-stu-id="72607-155">Analyze affected assets</span></span>

<span data-ttu-id="72607-156">Der Abschnitt **"Durchgeführte Aktionen"** enthält eine Liste der betroffenen Ressourcen, z. B. Postfächer, Geräte und Benutzer, die von dieser Warnung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="72607-156">The **Actions taken** section has a list of impacted assets, such as mailboxes, devices, and users affected by this alert.</span></span> 

<span data-ttu-id="72607-157">Sie können auch **im Info-Center** anzeigen auswählen, um die Registerkarte **"Verlauf"** des **Info-Centers** im Microsoft 365 Defender-Portal anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72607-157">You can also select **View in action center** to view the **History** tab of the **Action center** in the Microsoft 365 Defender portal.</span></span> 

### <a name="trace-an-alerts-role-in-the-alert-story"></a><span data-ttu-id="72607-158">Nachverfolgen der Rolle einer Warnung im Warnungsartikel</span><span class="sxs-lookup"><span data-stu-id="72607-158">Trace an alert's role in the alert story</span></span>

<span data-ttu-id="72607-159">Im Warnungsabschnitt werden alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72607-159">The alert story displays all assets or entities related to the alert in a process tree view.</span></span> <span data-ttu-id="72607-160">Die Warnung im Titel steht im Fokus, wenn Sie zum ersten Mal auf der Seite der ausgewählten Warnung landen.</span><span class="sxs-lookup"><span data-stu-id="72607-160">The alert in the title is the one in focus when you first land on your selected alert's page.</span></span> <span data-ttu-id="72607-161">Ressourcen im Warnungsartikel können erweitert und angeklickt werden.</span><span class="sxs-lookup"><span data-stu-id="72607-161">Assets in the alert story are expandable and clickable.</span></span> <span data-ttu-id="72607-162">Sie stellen zusätzliche Informationen bereit und beschleunigen Ihre Antwort, indem sie Es Ihnen ermöglichen, direkt im Kontext der Warnungsseite Maßnahmen zu ergreifen.</span><span class="sxs-lookup"><span data-stu-id="72607-162">They provide additional information and expedite your response by allowing you to take action right in the context of the alert page.</span></span> 

> [!NOTE]
> <span data-ttu-id="72607-163">Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, wobei zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur vor oder nach der ausgewählten Warnung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="72607-163">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

### <a name="view-more-alert-information-on-the-details-page"></a><span data-ttu-id="72607-164">Weitere Warnungsinformationen auf der Detailseite anzeigen</span><span class="sxs-lookup"><span data-stu-id="72607-164">View more alert information on the details page</span></span>

<span data-ttu-id="72607-165">Auf der Detailseite werden die Details der ausgewählten Warnung mit details und Aktionen im Zusammenhang mit der Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="72607-165">The details page shows the details of the selected alert, with details and actions related to it.</span></span> <span data-ttu-id="72607-166">Wenn Sie eine der betroffenen Ressourcen oder Entitäten im Warnungsartikel auswählen, wird die Detailseite so geändert, dass kontextbezogene Informationen und Aktionen für das ausgewählte Objekt bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="72607-166">If you select any of the affected assets or entities in the alert story, the details page changes to provide contextual information and actions for the selected object.</span></span>

<span data-ttu-id="72607-167">Nachdem Sie eine interessante Entität ausgewählt haben, ändert sich die Detailseite, um Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn diese verfügbar sind, und Optionen zum Ergreifen von Maßnahmen für diese Entität direkt über die Warnungsseite anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72607-167">Once you've selected an entity of interest, the details page changes to display information about the selected entity type, historic information when it's available, and options to take action on this entity directly from the alert page.</span></span>

## <a name="manage-alerts"></a><span data-ttu-id="72607-168">Verwalten von Warnungen</span><span class="sxs-lookup"><span data-stu-id="72607-168">Manage alerts</span></span>

<span data-ttu-id="72607-169">Um eine Warnung zu verwalten, wählen Sie die Warnung in der Warnungswarteschlange in der Zeile aus, um einen **Warnungsbereich verwalten** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="72607-169">To manage an alert, select the alert in the alerts queue on its row to see a **Manage alert** pane.</span></span> <span data-ttu-id="72607-170">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72607-170">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Beispiel für den Zusammenfassungsbereich für eine Warnung":::

<span data-ttu-id="72607-172">Im **Bereich "Warnung verwalten"** können Sie Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="72607-172">The **Manage alert** pane allows you to specify:</span></span>

- <span data-ttu-id="72607-173">Der Warnungsstatus (Neu, Aufgelöst, In Bearbeitung).</span><span class="sxs-lookup"><span data-stu-id="72607-173">The alert status (New, Resolved, In progress).</span></span>
- <span data-ttu-id="72607-174">Die Klassifizierung der Warnung (Nicht festgelegt, True-Warnung, False-Warnung).</span><span class="sxs-lookup"><span data-stu-id="72607-174">The alert's classification  (Not set, True alert, False Alert).</span></span>
- <span data-ttu-id="72607-175">Für die Klassifizierung als echte Warnung gibt die Art der Bedrohung für die Warnung im Feld **"Bestimmung"** an.</span><span class="sxs-lookup"><span data-stu-id="72607-175">For the classification as a true alert, the type of threat for the alert in **Determination** field.</span></span>
- <span data-ttu-id="72607-176">Ein Kommentar zur Warnung.</span><span class="sxs-lookup"><span data-stu-id="72607-176">A comment on the alert.</span></span>

> [!NOTE]
> <span data-ttu-id="72607-177">Eine Möglichkeit zum Verwalten von Warnungen durch die Verwendung von Tags.</span><span class="sxs-lookup"><span data-stu-id="72607-177">One way of managing alerts it through the use of tags.</span></span> <span data-ttu-id="72607-178">Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell eingeführt und befindet sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="72607-178">The tagging capability for Microsoft Defender for Office 365 is incrementally being rolled out and is currently in preview.</span></span> <br>
> <span data-ttu-id="72607-179">Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die *nach* dem Update erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="72607-179">Currently, modified tag names are only applied to alerts created *after* the update.</span></span> <span data-ttu-id="72607-180">Warnungen, die vor der Änderung generiert wurden, geben den aktualisierten Tagnamen nicht wieder.</span><span class="sxs-lookup"><span data-stu-id="72607-180">Alerts that were generated before the modification will not reflect the updated tag name.</span></span> 

<span data-ttu-id="72607-181">In diesem Bereich können Sie auch die folgenden zusätzlichen Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="72607-181">From this pane, you can also perform these additional actions:</span></span> 

- <span data-ttu-id="72607-182">Öffnen der Hauptwarnungsseite</span><span class="sxs-lookup"><span data-stu-id="72607-182">Open the main alert page</span></span>
- <span data-ttu-id="72607-183">Wenden Sie sich an einen Microsoft-Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="72607-183">Consult a Microsoft threat expert</span></span>
- <span data-ttu-id="72607-184">Anzeigen der Übermittlung</span><span class="sxs-lookup"><span data-stu-id="72607-184">View submission</span></span>
- <span data-ttu-id="72607-185">Link zu einem anderen Vorfall</span><span class="sxs-lookup"><span data-stu-id="72607-185">Link to another incident</span></span>
- <span data-ttu-id="72607-186">Anzeigen der Warnung auf einer Zeitachse</span><span class="sxs-lookup"><span data-stu-id="72607-186">See the alert in a timeline</span></span>
- <span data-ttu-id="72607-187">Erstellen einer Unterdrückungsregel</span><span class="sxs-lookup"><span data-stu-id="72607-187">Create a suppression rule</span></span>

<span data-ttu-id="72607-188">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="72607-188">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Beispiel für die Aktionen für eine Warnung im Microsoft 365 Defender Portal":::

<span data-ttu-id="72607-190">Die Liste der zusätzlichen Aktionen hängt vom Typ der Warnung ab.</span><span class="sxs-lookup"><span data-stu-id="72607-190">The list of additional actions depends on the type of alert.</span></span>

## <a name="resolve-an-alert"></a><span data-ttu-id="72607-191">Auflösen einer Warnung</span><span class="sxs-lookup"><span data-stu-id="72607-191">Resolve an alert</span></span>

<span data-ttu-id="72607-192">Sobald Sie mit der Analyse einer Warnung fertig sind und sie aufgelöst werden kann, wechseln Sie zum **Warnungsbereich "Warnung verwalten"** für die Warnung, und markieren Sie den Status **"Gelöst",** und klassifizieren Sie sie als **"False"** oder **"True".**</span><span class="sxs-lookup"><span data-stu-id="72607-192">Once you're done analyzing an alert and it can be resolved, go to the **Manage alert** pane for the alert and mark the it status as **Resolved** and classify it as either a **False alert** or **True alert**.</span></span> <span data-ttu-id="72607-193">Geben Sie für echte Warnungen den Bedrohungstyp der Warnung im **Feld "Bestimmung"** an.</span><span class="sxs-lookup"><span data-stu-id="72607-193">For true alerts, specify the alert's threat type in the **Determination** field.</span></span>

<span data-ttu-id="72607-194">Das Klassifizieren von Warnungen und die Angabe ihrer Bestimmung hilft bei der Optimierung Microsoft 365 Defender, um mehr echte und weniger falsche Warnungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="72607-194">Classifying alerts and specifying their determination helps tune Microsoft 365 Defender to provide more true alerts and less false alerts.</span></span>

## <a name="next-steps"></a><span data-ttu-id="72607-195">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="72607-195">Next steps</span></span>

<span data-ttu-id="72607-196">Setzen Sie Ihre [Untersuchung](investigate-incidents.md)nach Bedarf für In-Process-Vorfälle fort.</span><span class="sxs-lookup"><span data-stu-id="72607-196">As needed for in-process incidents, continue your [investigation](investigate-incidents.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="72607-197">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72607-197">See also</span></span>

- [<span data-ttu-id="72607-198">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="72607-198">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="72607-199">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="72607-199">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="72607-200">Untersuchen von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="72607-200">Investigate incidents</span></span>](investigate-incidents.md)

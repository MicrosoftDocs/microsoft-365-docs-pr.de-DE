---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen Sie Vorfälle, die auf Geräten, Benutzern und Postfächern im Microsoft 365 Defender-Portal angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reagieren, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365, Reaktion auf Vorfälle, Cyberangriff
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
ms.openlocfilehash: b6830c77a0c5cc93ea202844a8793c5f69f07650
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028523"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="27db6-104">Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27db6-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="27db6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="27db6-105">**Applies to:**</span></span>
- <span data-ttu-id="27db6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27db6-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="27db6-107">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="27db6-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="27db6-108">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="27db6-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="27db6-109">Ein Vorfall in Microsoft 365 Defender ist eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs bilden.</span><span class="sxs-lookup"><span data-stu-id="27db6-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="27db6-110">Microsoft 365 Dienste und Apps warnungen erstellen, wenn sie ein verdächtiges oder bösartiges Ereignis oder eine schädliche Aktivität erkennen.</span><span class="sxs-lookup"><span data-stu-id="27db6-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="27db6-111">Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff.</span><span class="sxs-lookup"><span data-stu-id="27db6-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="27db6-112">Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Entitätstypen verwendet, z. B. Geräte, Benutzer und Postfächer.</span><span class="sxs-lookup"><span data-stu-id="27db6-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="27db6-113">Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="27db6-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="27db6-114">Da es schwierig und zeitaufwändig sein kann, die einzelnen Warnungen zusammenzufassen, um Einblicke in einen Angriff zu erhalten, aggregiert Microsoft 365 Defender automatisch die Warnungen und die zugehörigen Informationen zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="27db6-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="So korreliert Microsoft 365 Defender Ereignisse von Entitäten in einen Vorfall":::

<span data-ttu-id="27db6-116">Sehen Sie sich diese kurze Übersicht über Vorfälle in Microsoft 365 Defender (4 Minuten) an.</span><span class="sxs-lookup"><span data-stu-id="27db6-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="27db6-117">Die Gruppierung verwandter Warnungen zu einem Vorfall bietet ihnen einen umfassenden Überblick über einen Angriff.</span><span class="sxs-lookup"><span data-stu-id="27db6-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="27db6-118">Sie können z. B. Folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="27db6-118">For example, you can see:</span></span>

- <span data-ttu-id="27db6-119">Wo der Angriff begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="27db6-119">Where the attack started.</span></span>
- <span data-ttu-id="27db6-120">Welche Taktiken verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="27db6-120">What tactics were used.</span></span>
- <span data-ttu-id="27db6-121">Wie weit der Angriff auf Ihren Mandanten gestoßen ist.</span><span class="sxs-lookup"><span data-stu-id="27db6-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="27db6-122">Der Umfang des Angriffs, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="27db6-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="27db6-123">Alle dem Angriff zugeordneten Daten.</span><span class="sxs-lookup"><span data-stu-id="27db6-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="27db6-124">Wenn [diese Option aktiviert](m365d-enable.md)ist, können Microsoft 365 Defender Warnungen durch Automatisierung und künstliche Intelligenz automatisch untersuchen und [beheben.](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="27db6-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can [automatically investigate and resolve](m365d-autoir.md) alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="27db6-125">Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben.</span><span class="sxs-lookup"><span data-stu-id="27db6-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-defender-portal"></a><span data-ttu-id="27db6-126">Vorfälle und Warnungen im Microsoft 365 Defender Portal</span><span class="sxs-lookup"><span data-stu-id="27db6-126">Incidents and alerts in the Microsoft 365 Defender portal</span></span>

<span data-ttu-id="27db6-127">Sie verwalten Vorfälle aus **Vorfällen & Warnungen > Vorfällen** im Schnellstart des Microsoft 365 Defender-Portals ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="27db6-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 Defender portal ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="27db6-128">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="27db6-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Defender-Portal":::

<span data-ttu-id="27db6-130">Wenn Sie einen Vorfallnamen auswählen, wird eine Zusammenfassung des Vorfalls angezeigt und der Zugriff auf Registerkarten mit zusätzlichen Informationen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="27db6-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Seite &quot;Zusammenfassung&quot; für einen Vorfall im portal Microsoft 365 Defender":::

<span data-ttu-id="27db6-132">Die zusätzlichen Registerkarten für einen Vorfall sind:</span><span class="sxs-lookup"><span data-stu-id="27db6-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="27db6-133">Warnungen</span><span class="sxs-lookup"><span data-stu-id="27db6-133">Alerts</span></span> 

  <span data-ttu-id="27db6-134">Alle Warnungen im Zusammenhang mit dem Vorfall und deren Informationen.</span><span class="sxs-lookup"><span data-stu-id="27db6-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="27db6-135">Geräte</span><span class="sxs-lookup"><span data-stu-id="27db6-135">Devices</span></span>

  <span data-ttu-id="27db6-136">Alle Geräte, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="27db6-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="27db6-137">Benutzer</span><span class="sxs-lookup"><span data-stu-id="27db6-137">Users</span></span>

  <span data-ttu-id="27db6-138">Alle Benutzer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="27db6-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="27db6-139">Postfächer</span><span class="sxs-lookup"><span data-stu-id="27db6-139">Mailboxes</span></span>

  <span data-ttu-id="27db6-140">Alle Postfächer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="27db6-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="27db6-141">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="27db6-141">Investigations</span></span>

  <span data-ttu-id="27db6-142">Alle [automatisierten Untersuchungen,](m365d-autoir.md) die durch Warnungen im Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="27db6-142">All the [automated investigations](m365d-autoir.md) triggered by alerts in the incident.</span></span>

- <span data-ttu-id="27db6-143">Nachweise und Antworten</span><span class="sxs-lookup"><span data-stu-id="27db6-143">Evidence and Response</span></span>

  <span data-ttu-id="27db6-144">Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen des Vorfalls.</span><span class="sxs-lookup"><span data-stu-id="27db6-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

- <span data-ttu-id="27db6-145">Graph (in der Vorschau)</span><span class="sxs-lookup"><span data-stu-id="27db6-145">Graph (in preview)</span></span>

  <span data-ttu-id="27db6-146">Abbildung der Verbindung von Warnungen mit den betroffenen Ressourcen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="27db6-146">A figure showing the connection of alerts to the impacted assets in your organization.</span></span>

<span data-ttu-id="27db6-147">Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten sowie die Registerkarten eines Vorfalls im portal Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="27db6-147">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Defender Portal":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="27db6-149">Beispielworkflow für die Reaktion auf Vorfälle für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27db6-149">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="27db6-150">Hier ist ein Beispielworkflow für die Reaktion auf Vorfälle in Microsoft 365 mit dem Microsoft 365 Defender-Portal.</span><span class="sxs-lookup"><span data-stu-id="27db6-150">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 Defender portal.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Beispiel für einen Vorfallreaktionsworkflow für Microsoft 365":::

<span data-ttu-id="27db6-152">Identifizieren Sie fortlaufend die Vorfälle mit der höchsten Priorität für Analyse und Lösung in der Vorfallswarteschlange, und bereiten Sie sie für die Reaktion vor.</span><span class="sxs-lookup"><span data-stu-id="27db6-152">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="27db6-153">Dies ist eine Kombination aus:</span><span class="sxs-lookup"><span data-stu-id="27db6-153">This is a combination of:</span></span>

- <span data-ttu-id="27db6-154">[Ermittlung](incident-queue.md) der Vorfälle mit der höchsten Priorität durch Filtern und Sortieren der Vorfallswarteschlange.</span><span class="sxs-lookup"><span data-stu-id="27db6-154">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="27db6-155">[Verwalten](manage-incidents.md) von Vorfällen durch Ändern ihres Titels, Zuweisen zu einem Analysten und Hinzufügen von Tags und Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="27db6-155">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="27db6-156">Beginnen Sie für jeden Vorfall mit einer Untersuchung und Analyse von [Angriffen und Warnungen:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="27db6-156">For each incident, begin an [attack and alert investigation and analysis](investigate-incidents.md):</span></span>
 
   1. <span data-ttu-id="27db6-157">Sehen Sie sich die Zusammenfassung des Vorfalls an, um den Umfang und Schweregrad des Vorfalls und die betroffenen Entitäten zu verstehen (Registerkarte **"Zusammenfassung").**</span><span class="sxs-lookup"><span data-stu-id="27db6-157">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   1. <span data-ttu-id="27db6-158">Beginnen Sie mit der Analyse der Warnungen, um deren Ursprung, Umfang und Schweregrad zu verstehen (Registerkarte **"Warnungen").**</span><span class="sxs-lookup"><span data-stu-id="27db6-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   1. <span data-ttu-id="27db6-159">Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (registerkarten **"Geräte",** **"Benutzer"** und **"Postfächer").**</span><span class="sxs-lookup"><span data-stu-id="27db6-159">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   1. <span data-ttu-id="27db6-160">Erfahren Sie, wie Microsoft 365 Defender [einige Warnungen automatisch aufgelöst](m365d-autoir.md) hat (Registerkarte **"Untersuchungen").**</span><span class="sxs-lookup"><span data-stu-id="27db6-160">See how Microsoft 365 Defender has [automatically resolved some alerts](m365d-autoir.md) (the **Investigations** tab).</span></span>
   
   1. <span data-ttu-id="27db6-161">Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **"Nachweise und Reaktion").**</span><span class="sxs-lookup"><span data-stu-id="27db6-161">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="27db6-162">Führen Sie nach oder während Ihrer Analyse eine Eindämmung durch, um die zusätzlichen Auswirkungen des Angriffs und die Beseitigung der Sicherheitsrisiken zu verringern.</span><span class="sxs-lookup"><span data-stu-id="27db6-162">After or during your analysis, perform containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="27db6-163">Wiederherstellen Sie nach dem Angriff so weit wie möglich, indem Sie Ihre Mandantenressourcen in den Zustand wiederherstellen, in dem sie sich vor dem Vorfall befanden.</span><span class="sxs-lookup"><span data-stu-id="27db6-163">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="27db6-164">[Beheben Sie](manage-incidents.md#resolve-an-incident) den Vorfall, und nehmen Sie sich Zeit, um nach dem Vorfall zu lernen:</span><span class="sxs-lookup"><span data-stu-id="27db6-164">[Resolve](manage-incidents.md#resolve-an-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="27db6-165">Verstehen sie den Typ des Angriffs und seine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="27db6-165">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="27db6-166">Untersuchen Sie den Angriff in [Threat Analytics](threat-analytics.md) und die Sicherheitscommunity nach einem Trend bei Sicherheitsangriffen.</span><span class="sxs-lookup"><span data-stu-id="27db6-166">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="27db6-167">Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre standardmäßigen Workflows, Prozesse, Richtlinien und Playbooks nach Bedarf zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="27db6-167">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="27db6-168">Ermitteln Sie, ob Änderungen in Ihrer Sicherheitskonfiguration erforderlich sind, und implementieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="27db6-168">Determine whether changes in your security configuration are needed and implement them.</span></span>

<span data-ttu-id="27db6-169">Wenn Sie noch keine Informationen zur Sicherheitsanalyse haben, lesen Sie die Einführung in die [Reaktion auf Ihren ersten Vorfall,](incidents-overview.md) um weitere Informationen zu erhalten und einen Beispielvorfall durchzugehen.</span><span class="sxs-lookup"><span data-stu-id="27db6-169">If you are new to security analysis, see the [introduction to responding to your first incident](incidents-overview.md) for additional information and to step through an example incident.</span></span>

<span data-ttu-id="27db6-170">Weitere Informationen zur Behandlung von Sicherheitsvorfällen in Microsoft-Produkten finden Sie in [diesem Artikel.](/security/compass/incident-response-overview)</span><span class="sxs-lookup"><span data-stu-id="27db6-170">For more information about incident response across Microsoft products, see [this article](/security/compass/incident-response-overview).</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="27db6-171">Beispielsicherheitsvorgänge für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="27db6-171">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="27db6-172">Hier ist ein Beispiel für Sicherheitsvorgänge (SecOps) für Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="27db6-172">Here's an example of security operations (SecOps) for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ein Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender":::

<span data-ttu-id="27db6-174">Tägliche Aufgaben können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="27db6-174">Daily tasks can include:</span></span>

- <span data-ttu-id="27db6-175">[Verwalten von](manage-incidents.md) Vorfällen</span><span class="sxs-lookup"><span data-stu-id="27db6-175">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="27db6-176">Überprüfen von [AIR-Aktionen (Automated Investigation and Response)](m365d-action-center.md) im Info-Center</span><span class="sxs-lookup"><span data-stu-id="27db6-176">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions in the Action center</span></span>
- <span data-ttu-id="27db6-177">Überprüfen der neuesten [Bedrohungsanalyse](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="27db6-177">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="27db6-178">[Reaktion auf](investigate-incidents.md) Vorfälle</span><span class="sxs-lookup"><span data-stu-id="27db6-178">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="27db6-179">Monatliche Aufgaben können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="27db6-179">Monthly tasks can include:</span></span>

- <span data-ttu-id="27db6-180">Überprüfen von [AIR-Einstellungen](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="27db6-180">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="27db6-181">Überprüfen der [Sicherheitsbewertung](microsoft-secure-score-improvement-actions.md) und [& Sicherheitsrisikoverwaltung](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="27db6-181">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="27db6-182">Berichterstellung für Ihre IT-Sicherheitsverwaltungskette</span><span class="sxs-lookup"><span data-stu-id="27db6-182">Reporting to your IT security management chain</span></span>

<span data-ttu-id="27db6-183">Vierteljährliche Aufgaben können einen Bericht und ein Briefing der Sicherheitsergebnisse an den Chief Information Security Officer (CISO) umfassen.</span><span class="sxs-lookup"><span data-stu-id="27db6-183">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="27db6-184">Jährliche Aufgaben können die Durchführung eines größeren Vorfalls oder einer Verletzungsübung umfassen, um Ihre Mitarbeiter, Systeme und Prozesse zu testen.</span><span class="sxs-lookup"><span data-stu-id="27db6-184">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="27db6-185">Tägliche, monatliche, vierteljährliche und jährliche Aufgaben können verwendet werden, um Prozesse, Richtlinien und Sicherheitskonfigurationen zu aktualisieren oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="27db6-185">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

### <a name="secops-resources-across-microsoft-products"></a><span data-ttu-id="27db6-186">SecOps-Ressourcen in microsoftweiten Produkten</span><span class="sxs-lookup"><span data-stu-id="27db6-186">SecOps resources across Microsoft products</span></span>

<span data-ttu-id="27db6-187">Weitere Informationen zu SecOps in allen Microsoft-Produkten finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="27db6-187">For more information about SecOps across Microsoft's products, see these resources:</span></span>

- [<span data-ttu-id="27db6-188">Capabilities</span><span class="sxs-lookup"><span data-stu-id="27db6-188">Capabilities</span></span>](/security/compass/security-operations-capabilities)
- [<span data-ttu-id="27db6-189">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="27db6-189">Best practices</span></span>](/security/compass/security-operations)
- [<span data-ttu-id="27db6-190">Videos und Folien</span><span class="sxs-lookup"><span data-stu-id="27db6-190">Videos and slides</span></span>](/security/compass/security-operations-videos-and-decks)

## <a name="next-steps"></a><span data-ttu-id="27db6-191">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="27db6-191">Next steps</span></span>

<span data-ttu-id="27db6-192">**Wenn Sie noch keine Informationen** zur Sicherheitsanalyse und zur Reaktion auf Sicherheitsvorfälle haben:</span><span class="sxs-lookup"><span data-stu-id="27db6-192">**If you are new** to security analysis and incident response:</span></span>

- <span data-ttu-id="27db6-193">Sehen Sie sich die [exemplarische Vorgehensweise zum Reagieren auf Ihren ersten Vorfall an,](first-incident-overview.md) um eine Führung durch einen typischen Prozess der Analyse, Behebung und Überprüfung nach dem Vorfall im Microsoft 365 Defender-Portal mit einem Beispielangriff zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="27db6-193">See the [Respond to your first incident walkthrough](first-incident-overview.md) to get a guided tour of a typical process of analysis, remediation, and post-incident review in the Microsoft 365 Defender portal with an example attack.</span></span>

<span data-ttu-id="27db6-194">**Wenn Sie Erfahrung** mit Sicherheitsanalysen und der Reaktion auf Vorfälle haben:</span><span class="sxs-lookup"><span data-stu-id="27db6-194">**If you have experience** with security analysis and incident response:</span></span>

- <span data-ttu-id="27db6-195">Erste Schritte mit der Vorfallwarteschlange auf der Seite **"Vorfälle"** des Microsoft 365 Defender-Portals.</span><span class="sxs-lookup"><span data-stu-id="27db6-195">Get started with the incident queue from the **Incidents** page of the Microsoft 365 Defender portal.</span></span> <span data-ttu-id="27db6-196">Von hier aus haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="27db6-196">From here, you can:</span></span>

  - <span data-ttu-id="27db6-197">Erfahren Sie, welche Vorfälle basierend auf dem Schweregrad und anderen Faktoren [priorisiert](incident-queue.md) werden sollten.</span><span class="sxs-lookup"><span data-stu-id="27db6-197">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 

  - <span data-ttu-id="27db6-198">[Verwalten Von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags und Kommentaren basierend auf Ihrem Vorfallverwaltungsworkflow.</span><span class="sxs-lookup"><span data-stu-id="27db6-198">[Manage incidents](manage-incidents.md), which includes renaming, assigning, classifying, and adding tags and comments based on your incident management workflow.</span></span>

  - <span data-ttu-id="27db6-199">Führen Sie [Untersuchungen](investigate-incidents.md) von Vorfällen durch.</span><span class="sxs-lookup"><span data-stu-id="27db6-199">Perform [investigations](investigate-incidents.md) of incidents.</span></span>

- <span data-ttu-id="27db6-200">In diesen Playbooks zur Behandlung von [Sicherheitsvorfällen](/security/compass/incident-response-playbooks) finden Sie ausführliche Anleitungen für Phishing-, Kennwort-Spray- und App-Genehmigungs-Angriffe.</span><span class="sxs-lookup"><span data-stu-id="27db6-200">See these [incident response playbooks](/security/compass/incident-response-playbooks) for detailed guidance for phishing, password spray, and app consent grant attacks.</span></span>


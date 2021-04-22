---
title: Vorfälle in Microsoft 365 Defender
description: Untersuchen sie Vorfälle, die auf Geräten, Benutzern und Postfächern im Microsoft 365 Security Center angezeigt werden.
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
ms.openlocfilehash: 890e64367c49c24c8c70e2cbda9869a5d0797219
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939586"
---
# <a name="incidents-in-microsoft-365-defender"></a><span data-ttu-id="fd002-104">Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd002-104">Incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd002-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fd002-105">**Applies to:**</span></span>
- <span data-ttu-id="fd002-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd002-106">Microsoft 365 Defender</span></span>

> <span data-ttu-id="fd002-107">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="fd002-107">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="fd002-108">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="fd002-108">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

<span data-ttu-id="fd002-109">Bei einem Vorfall in Microsoft 365 Defender handelt es sich um eine Sammlung korrelierter Warnungen und zugehöriger Daten, die die Geschichte eines Angriffs enthalten.</span><span class="sxs-lookup"><span data-stu-id="fd002-109">An incident in Microsoft 365 Defender is a collection of correlated alerts and associated data that make up the story of an attack.</span></span> 

<span data-ttu-id="fd002-110">Microsoft 365-Dienste und -Apps erstellen Warnungen, wenn sie ein verdächtiges oder böswilliges Ereignis oder eine Aktivität erkennen.</span><span class="sxs-lookup"><span data-stu-id="fd002-110">Microsoft 365 services and apps create alerts when they detect a suspicious or malicious event or activity.</span></span> <span data-ttu-id="fd002-111">Einzelne Warnungen liefern wertvolle Hinweise zu einem abgeschlossenen oder laufenden Angriff.</span><span class="sxs-lookup"><span data-stu-id="fd002-111">Individual alerts provide valuable clues about a completed or ongoing attack.</span></span> <span data-ttu-id="fd002-112">Bei Angriffen werden jedoch in der Regel verschiedene Techniken gegen verschiedene Typen von Entitäten verwendet, z. B. Geräte, Benutzer und Postfächer.</span><span class="sxs-lookup"><span data-stu-id="fd002-112">However, attacks typically employ various techniques against different types of entities, such as devices, users, and mailboxes.</span></span> <span data-ttu-id="fd002-113">Das Ergebnis sind mehrere Warnungen für mehrere Entitäten in Ihrem Mandanten.</span><span class="sxs-lookup"><span data-stu-id="fd002-113">The result is multiple alerts for multiple entities in your tenant.</span></span> 

<span data-ttu-id="fd002-114">Da das Verbinden der einzelnen Warnungen, um Einblick in einen Angriff zu erhalten, eine Herausforderung und zeitaufwändige Aufgabe sein kann, aggregiert Microsoft 365 Defender die Warnungen und ihre zugehörigen Informationen automatisch zu einem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="fd002-114">Because piecing the individual alerts together to gain insight into an attack can be challenging and time-consuming, Microsoft 365 Defender automatically aggregates the alerts and their associated information into an incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Korrelieren von Ereignissen von Entitäten zu einem Vorfall in Microsoft 365 Defender":::

<span data-ttu-id="fd002-116">Sehen Sie sich diese kurze Übersicht über Vorfälle in Microsoft 365 Defender (4 Minuten) an.</span><span class="sxs-lookup"><span data-stu-id="fd002-116">Watch this short overview of incidents in Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

<span data-ttu-id="fd002-117">Durch das Gruppieren verwandter Warnungen zu einem Vorfall erhalten Sie eine umfassende Ansicht eines Angriffs.</span><span class="sxs-lookup"><span data-stu-id="fd002-117">Grouping related alerts into an incident gives you a comprehensive view of an attack.</span></span> <span data-ttu-id="fd002-118">Sie können z. B. folgende Informationen sehen:</span><span class="sxs-lookup"><span data-stu-id="fd002-118">For example, you can see:</span></span>

- <span data-ttu-id="fd002-119">An der Stelle, an der der Angriff begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="fd002-119">Where the attack started.</span></span>
- <span data-ttu-id="fd002-120">Welche Taktiken verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="fd002-120">What tactics were used.</span></span>
- <span data-ttu-id="fd002-121">Wie weit der Angriff in Ihren Mandanten gegangen ist.</span><span class="sxs-lookup"><span data-stu-id="fd002-121">How far the attack has gone into your tenant.</span></span>
- <span data-ttu-id="fd002-122">Der Umfang des Angriffs, z. B. wie viele Geräte, Benutzer und Postfächer betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="fd002-122">The scope of the attack, such as how many devices, users, and mailboxes were impacted.</span></span> 
- <span data-ttu-id="fd002-123">Alle dem Angriff zugeordneten Daten.</span><span class="sxs-lookup"><span data-stu-id="fd002-123">All of the data associated with the attack.</span></span>

<span data-ttu-id="fd002-124">Wenn [diese Option](m365d-enable.md)aktiviert ist, kann Microsoft 365 Defender Warnungen automatisch durch Automatisierung und künstliche Intelligenz untersuchen und auflösen.</span><span class="sxs-lookup"><span data-stu-id="fd002-124">If [enabled](m365d-enable.md), Microsoft 365 Defender can automatically investigate and resolve alerts through automation and artificial intelligence.</span></span> <span data-ttu-id="fd002-125">Sie können auch zusätzliche Korrekturschritte ausführen, um den Angriff zu beheben.</span><span class="sxs-lookup"><span data-stu-id="fd002-125">You can also perform additional remediation steps to resolve the attack.</span></span> 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a><span data-ttu-id="fd002-126">Vorfälle und Warnungen im Microsoft 365 Security Center</span><span class="sxs-lookup"><span data-stu-id="fd002-126">Incidents and alerts in the Microsoft 365 security center</span></span>

<span data-ttu-id="fd002-127">Sie verwalten Vorfälle aus Vorfällen **& Warnungen > Vorfällen** beim Schnellstart des Microsoft 365 Security Centers ([security.microsoft.com](https://security.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="fd002-127">You manage incidents from **Incidents & alerts > Incidents** on the quick launch of the Microsoft 365 security center ([security.microsoft.com](https://security.microsoft.com)).</span></span> <span data-ttu-id="fd002-128">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="fd002-128">Here's an example.</span></span>

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Die Seite &quot;Vorfälle&quot; im Microsoft 365 Security Center":::

<span data-ttu-id="fd002-130">Wenn Sie einen Vorfallnamen auswählen, wird eine Zusammenfassung des Vorfalls und der Zugriff auf Registerkarten mit zusätzlichen Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fd002-130">Selecting an incident name displays a summary of the incident and provides access to tabs with additional information.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Zusammenfassungsseite für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="fd002-132">Die zusätzlichen Registerkarten für einen Vorfall sind:</span><span class="sxs-lookup"><span data-stu-id="fd002-132">The additional tabs for an incident are:</span></span>

- <span data-ttu-id="fd002-133">Warnungen</span><span class="sxs-lookup"><span data-stu-id="fd002-133">Alerts</span></span> 

  <span data-ttu-id="fd002-134">Alle Warnungen im Zusammenhang mit dem Vorfall und deren Informationen.</span><span class="sxs-lookup"><span data-stu-id="fd002-134">All the alerts related to the incident and their information.</span></span>

- <span data-ttu-id="fd002-135">Geräte</span><span class="sxs-lookup"><span data-stu-id="fd002-135">Devices</span></span>

  <span data-ttu-id="fd002-136">Alle Geräte, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd002-136">All the devices that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fd002-137">Benutzer</span><span class="sxs-lookup"><span data-stu-id="fd002-137">Users</span></span>

  <span data-ttu-id="fd002-138">Alle Benutzer, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd002-138">All the users that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fd002-139">Postfächer</span><span class="sxs-lookup"><span data-stu-id="fd002-139">Mailboxes</span></span>

  <span data-ttu-id="fd002-140">Alle Postfächer, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="fd002-140">All the mailboxes that have been identified to be part of or related to the incident.</span></span>

- <span data-ttu-id="fd002-141">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="fd002-141">Investigations</span></span>

  <span data-ttu-id="fd002-142">Alle automatisierten Untersuchungen, die durch Warnungen im Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="fd002-142">All the automated investigations triggered by alerts in the incident.</span></span>

- <span data-ttu-id="fd002-143">Nachweis und Antwort</span><span class="sxs-lookup"><span data-stu-id="fd002-143">Evidence and Response</span></span>

  <span data-ttu-id="fd002-144">Alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall.</span><span class="sxs-lookup"><span data-stu-id="fd002-144">All the supported events and suspicious entities in the alerts in the incident.</span></span>

<span data-ttu-id="fd002-145">Hier sehen Sie die Beziehung zwischen einem Vorfall und seinen Daten und den Registerkarten eines Vorfalls im Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd002-145">Here's the relationship between an incident and its data and the tabs of an incident in the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Die Beziehung eines Vorfalls und seiner Daten zu den Registerkarten eines Vorfalls im Microsoft 365 Security Center":::

## <a name="example-incident-response-workflow-for-microsoft-365-defender"></a><span data-ttu-id="fd002-147">Beispielworkflow zur Reaktion auf Vorfälle für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd002-147">Example incident response workflow for Microsoft 365 Defender</span></span>

<span data-ttu-id="fd002-148">Hier ist ein Beispielworkflow für die Reaktion auf Vorfälle in Microsoft 365 mit dem Microsoft 365 Security Center.</span><span class="sxs-lookup"><span data-stu-id="fd002-148">Here's an example workflow for responding to incidents in Microsoft 365 with the Microsoft 365 security center.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-workflow.png" alt-text="Beispiel für einen Workflow zur Reaktion auf Vorfälle für Microsoft 365":::

<span data-ttu-id="fd002-150">Identifizieren Sie fortlaufend die Vorfälle mit der höchsten Priorität für die Analyse und Lösung in der Vorfallwarteschlange, und bereiten Sie sie für die Reaktion vor.</span><span class="sxs-lookup"><span data-stu-id="fd002-150">On an ongoing basis, identify the highest priority incidents for analysis and resolution in the incident queue and get them ready for response.</span></span> <span data-ttu-id="fd002-151">Dies ist eine Kombination aus:</span><span class="sxs-lookup"><span data-stu-id="fd002-151">This is a combination of:</span></span>

- <span data-ttu-id="fd002-152">[Triaging](incident-queue.md) zur Ermittlung der Vorfälle mit höchster Priorität durch Filtern und Sortieren der Vorfallwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="fd002-152">[Triaging](incident-queue.md) to determining the highest priority incidents through filtering and sorting of the incident queue.</span></span>
- <span data-ttu-id="fd002-153">[Verwalten](manage-incidents.md) von Vorfällen durch Ändern des Titels, Zuweisen zu einem Analysten und Hinzufügen von Tags und Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="fd002-153">[Managing](manage-incidents.md) incidents by modifying their title, assigning them to an analyst, and adding tags and comments.</span></span>

1. <span data-ttu-id="fd002-154">Beginnen Sie für jeden Vorfall mit einer [Angriffs- und Warnungsanalyse:](investigate-incidents.md)</span><span class="sxs-lookup"><span data-stu-id="fd002-154">For each incident, begin an [attack and alert analysis](investigate-incidents.md):</span></span>

   <span data-ttu-id="fd002-155">a.</span><span class="sxs-lookup"><span data-stu-id="fd002-155">a.</span></span> <span data-ttu-id="fd002-156">Zeigen Sie die Zusammenfassung des Vorfalls an, um den Umfang und den Schweregrad des Vorfalls sowie die betroffenen Entitäten zu verstehen (registerkarte **Zusammenfassung).**</span><span class="sxs-lookup"><span data-stu-id="fd002-156">View the summary of the incident to understand it's scope and severity and what entities are affected (the **Summary** tab).</span></span>

   <span data-ttu-id="fd002-157">b.</span><span class="sxs-lookup"><span data-stu-id="fd002-157">b.</span></span> <span data-ttu-id="fd002-158">Beginnen Sie mit der Analyse der Warnungen, um ihren Ursprung, Umfang und Schweregrad zu verstehen (registerkarte **Warnungen).**</span><span class="sxs-lookup"><span data-stu-id="fd002-158">Begin analyzing the alerts to understand their origin, scope, and severity (the **Alerts** tab).</span></span>

   <span data-ttu-id="fd002-159">c.</span><span class="sxs-lookup"><span data-stu-id="fd002-159">c.</span></span> <span data-ttu-id="fd002-160">Sammeln Sie bei Bedarf Informationen zu betroffenen Geräten, Benutzern und Postfächern (die Registerkarten **Geräte,** **Benutzer** **und** Postfächer).</span><span class="sxs-lookup"><span data-stu-id="fd002-160">As needed, gather information on impacted devices, users, and mailboxes (the **Devices**, **Users**, and **Mailboxes** tabs).</span></span>

   <span data-ttu-id="fd002-161">d.</span><span class="sxs-lookup"><span data-stu-id="fd002-161">d.</span></span> <span data-ttu-id="fd002-162">Erfahren Sie, wie Microsoft 365 Defender einige Warnungen automatisch aufgelöst hat (registerkarte **Untersuchungen).**</span><span class="sxs-lookup"><span data-stu-id="fd002-162">See how Microsoft 365 Defender has automatically resolved some alerts (the **Investigations** tab).</span></span>
   
   <span data-ttu-id="fd002-163">e.</span><span class="sxs-lookup"><span data-stu-id="fd002-163">e.</span></span> <span data-ttu-id="fd002-164">Verwenden Sie bei Bedarf Informationen im Datensatz für den Vorfall, um weitere Informationen zu erhalten (registerkarte **Nachweis und** Antwort).</span><span class="sxs-lookup"><span data-stu-id="fd002-164">As needed, use information in the data set for the incident for more information (the **Evidence and Response** tab).</span></span>

2. <span data-ttu-id="fd002-165">Adressieren Sie nach oder während der Analyse die Eindämmung, um zusätzliche Auswirkungen des Angriffs und der Beseitigung der Sicherheitsbedrohung zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="fd002-165">After or during your analysis, address containment to reduce any additional impact of the attack and eradication of the security threat.</span></span>

3. <span data-ttu-id="fd002-166">Wiederherstellen Sie so weit wie möglich nach dem Angriff, indem Sie Ihre Mandantenressourcen in dem Zustand wiederherstellen, in dem sie sich vor dem Vorfall auf dem Konto hatten.</span><span class="sxs-lookup"><span data-stu-id="fd002-166">As much as possible, recover from the attack by restoring your tenant resources to the state they were in before the incident.</span></span>

4. <span data-ttu-id="fd002-167">[Beheben](manage-incidents.md#resolve-incident) Sie den Vorfall, und nehmen Sie sich Zeit für das Lernen nach dem Vorfall:</span><span class="sxs-lookup"><span data-stu-id="fd002-167">[Resolve](manage-incidents.md#resolve-incident) the incident and take time for post-incident learning to:</span></span>

   - <span data-ttu-id="fd002-168">Verstehen sie den Typ des Angriffs und seine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="fd002-168">Understand the type of the attack and its impact.</span></span>
   - <span data-ttu-id="fd002-169">Forschen Sie den Angriff in [Threat Analytics](threat-analytics.md) und der Sicherheitsgemeinschaft nach einem Trend zu Sicherheitsangriffen.</span><span class="sxs-lookup"><span data-stu-id="fd002-169">Research the attack in [Threat Analytics](threat-analytics.md) and the security community for a security attack trend.</span></span>
   - <span data-ttu-id="fd002-170">Erinnern Sie sich an den Workflow, den Sie verwendet haben, um den Vorfall zu beheben und Ihre Standardworkflows, Prozesse, Richtlinien und Playbooks nach Bedarf zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="fd002-170">Recall the workflow you used to resolve the incident and update your standard workflows, processes, policies, and playbooks as needed.</span></span>
   - <span data-ttu-id="fd002-171">Bestimmen Sie, ob Änderungen in Ihrer Sicherheitskonfiguration erforderlich sind, und implementieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="fd002-171">Determine whether changes in your security configuration are needed and implement them.</span></span>

## <a name="example-security-operations-for-microsoft-365-defender"></a><span data-ttu-id="fd002-172">Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd002-172">Example security operations for Microsoft 365 Defender</span></span>

<span data-ttu-id="fd002-173">Im Folgenden finden Sie ein Beispiel für Sicherheitsvorgänge für Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="fd002-173">Here's an example of security operations for Microsoft 365 Defender.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-example-operations.png" alt-text="Ein Beispiel für Sicherheitsvorgänge für Micosoft 365 Defender":::

<span data-ttu-id="fd002-175">Zu den täglichen Aufgaben gehören:</span><span class="sxs-lookup"><span data-stu-id="fd002-175">Daily tasks can include:</span></span>

- <span data-ttu-id="fd002-176">[Verwalten von](manage-incidents.md) Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fd002-176">[Managing](manage-incidents.md) incidents</span></span>
- <span data-ttu-id="fd002-177">Überprüfen [automatisierter Untersuchungs- und Reaktionsaktionen (AIR)](m365d-action-center.md)</span><span class="sxs-lookup"><span data-stu-id="fd002-177">Reviewing [automated investigation and response (AIR)](m365d-action-center.md) actions</span></span>
- <span data-ttu-id="fd002-178">Überprüfen der neuesten [Bedrohungsanalyse](threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="fd002-178">Reviewing the latest [Threat Analytics](threat-analytics.md)</span></span>
- <span data-ttu-id="fd002-179">[Reagieren auf](investigate-incidents.md) Vorfälle</span><span class="sxs-lookup"><span data-stu-id="fd002-179">[Responding](investigate-incidents.md) to incidents</span></span>

<span data-ttu-id="fd002-180">Monatliche Aufgaben können Folgendes umfassen:</span><span class="sxs-lookup"><span data-stu-id="fd002-180">Monthly tasks can include:</span></span>

- <span data-ttu-id="fd002-181">Überprüfen [der AIR-Einstellungen](m365d-configure-auto-investigation-response.md)</span><span class="sxs-lookup"><span data-stu-id="fd002-181">Reviewing [AIR settings](m365d-configure-auto-investigation-response.md)</span></span>
- <span data-ttu-id="fd002-182">Überprüfen [der sicherheitssicheren Bewertung](microsoft-secure-score-improvement-actions.md) und & [Sicherheitsrisikoverwaltung](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span><span class="sxs-lookup"><span data-stu-id="fd002-182">Reviewing [Secure Score](microsoft-secure-score-improvement-actions.md) and [Threat & Vulnerability Management](../defender-endpoint/next-gen-threat-and-vuln-mgt.md)</span></span>
- <span data-ttu-id="fd002-183">Berichterstellung an Ihre IT-Sicherheitsverwaltungskette</span><span class="sxs-lookup"><span data-stu-id="fd002-183">Reporting to your IT security management chain</span></span>

<span data-ttu-id="fd002-184">Vierteljährliche Aufgaben können einen Bericht und ein Briefing der Sicherheitsergebnisse an den Chief Information Security Officer (CISO) enthalten.</span><span class="sxs-lookup"><span data-stu-id="fd002-184">Quarterly tasks can include a report and briefing of security results to the Chief Information Security Officer (CISO).</span></span>

<span data-ttu-id="fd002-185">Zu den jährlichen Aufgaben kann die Durchführung einer Größeren Vorfall- oder Verletzungsübung gehören, um Ihre Mitarbeiter, Systeme und Prozesse zu testen.</span><span class="sxs-lookup"><span data-stu-id="fd002-185">Annual tasks can include conducting a major incident or breach exercise to test your staff, systems, and processes.</span></span> 

<span data-ttu-id="fd002-186">Tägliche, monatliche, vierteljährliche und jährliche Aufgaben können verwendet werden, um Prozesse, Richtlinien und Sicherheitskonfigurationen zu aktualisieren oder zu verfeinern.</span><span class="sxs-lookup"><span data-stu-id="fd002-186">Daily, monthly, quarterly, and annual tasks can be used to update or refine processes, policies, and security configurations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fd002-187">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fd002-187">Next steps</span></span>

<span data-ttu-id="fd002-188">In der Warteschleife auf der **Seite** Vorfälle werden die neuesten Vorfälle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fd002-188">The incident queue from the **Incidents** page lists the most recent incidents.</span></span> <span data-ttu-id="fd002-189">Hier haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="fd002-189">From here, you can:</span></span>

- <span data-ttu-id="fd002-190">Sehen Sie sich an, welche [Vorfälle](incident-queue.md) basierend auf dem Schweregrad und anderen Faktoren priorisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fd002-190">See which incidents should be [prioritized](incident-queue.md) based on severity and other factors.</span></span> 
- <span data-ttu-id="fd002-191">[Verwalten von Vorfällen,](manage-incidents.md)einschließlich Umbenennen, Zuweisen, Klassifizieren und Hinzufügen von Tags und Kommentaren für Ihren Workflow für die Vorfallverwaltung.</span><span class="sxs-lookup"><span data-stu-id="fd002-191">[Manage incidents](manage-incidents.md), which includes renaming, assignment, classifying, and adding tags and comments for your incident management workflow.</span></span>
- <span data-ttu-id="fd002-192">Führen Sie [eine Analyse](investigate-incidents.md) eines Vorfalls durch.</span><span class="sxs-lookup"><span data-stu-id="fd002-192">Perform an [analysis](investigate-incidents.md) of an incident.</span></span>

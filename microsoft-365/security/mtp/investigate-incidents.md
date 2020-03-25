---
title: Untersuchen Sie Vorfälle in Microsoft Threat Protection
description: Analysieren Sie Vorfälle in Bezug auf Geräte, Nutzer und Postfächer.
keywords: Vorfall, Vorfälle, Rechner, Geräte, Nutzer, Identitäten, Post, E-Mail, Postfach, Untersuchung, Graph, Beweise
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
ms.openlocfilehash: 1883f61f50dad9b601329369bf180ddecba70138
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928962"
---
# <a name="investigate-incidents-in-microsoft-threat-protection"></a><span data-ttu-id="fa34a-104">Untersuchen Sie Vorfälle in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fa34a-104">Investigate incidents in Microsoft Threat Protection</span></span>

<span data-ttu-id="fa34a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="fa34a-105">**Applies to:**</span></span>

- <span data-ttu-id="fa34a-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="fa34a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="fa34a-107">Microsoft Threat Protection fasst alle zugehörigen Warnungen, Assets, Untersuchungen und Beweise auf Ihren Geräten, Nutzern und Postfächern zusammen, um Ihnen einen umfassenden Überblick über die gesamte Bandbreite eines Angriffs zu geben.</span><span class="sxs-lookup"><span data-stu-id="fa34a-107">Microsoft Threat Protection aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="fa34a-108">Untersuchen Sie die Warnmeldungen, die Ihr Netzwerk betreffen, verstehen Sie, was sie bedeuten, und stellen Sie die mit den Vorfällen verbundenen Beweise zusammen, damit Sie einen wirksamen Plan zur Behebung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="fa34a-109">Untersuchung eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="fa34a-109">Investigate an incident</span></span>

1. <span data-ttu-id="fa34a-110">Wählen Sie einen Vorfall aus der Vorfallwarteschlange aus.</span><span class="sxs-lookup"><span data-stu-id="fa34a-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="fa34a-111">Dadurch wird ein Seitenbereich geöffnet und eine Vorschau wichtiger Informationen wie Status, Schweregrad, Kategorien und betroffener Entitäten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa34a-111">This opens a side panel and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild eines Seitenbereichs](../../media/incident-side-panel.png)

2. <span data-ttu-id="fa34a-113">Wählen Sie **Vorfallseite öffnen**.</span><span class="sxs-lookup"><span data-stu-id="fa34a-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="fa34a-114">Daraufhin wird die Vorfallseite geöffnet, auf der Sie weitere Informationen zu Vorfällen, Kommentaren und Aktionen sowie Registerkarten (Übersicht, Warnungen, Geräte, Nutzer, Untersuchungen, Beweise) finden.</span><span class="sxs-lookup"><span data-stu-id="fa34a-114">This opens the incident page where you'll find more information incident details, comments and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="fa34a-115">Überprüfen Sie die Warnungen, Geräte, Nutzer und anderen Entitäten, die an dem Vorfall beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="fa34a-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="fa34a-116">Vorfall Übersicht</span><span class="sxs-lookup"><span data-stu-id="fa34a-116">Incident overview</span></span>

<span data-ttu-id="fa34a-117">Auf der Übersichtsseite erhalten Sie einen Überblick über die wichtigsten Informationen zu dem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="fa34a-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Abbildung der Vorfallübersichtsseite](../../media/incidents-overview.png)

<span data-ttu-id="fa34a-119">Die Angriffskategorien geben Ihnen eine visuelle und numerische Darstellung des Fortschritts des Angriffs gegen die Kill Chain.</span><span class="sxs-lookup"><span data-stu-id="fa34a-119">The attack categories give you visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="fa34a-120">Wie bei anderen Microsoft-Sicherheitsprodukten ist auch Microsoft Threat Protection auf das Framework [MITRE ATT&CK&trade;](https://attack.mitre.org/) ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="fa34a-120">As with other Microsoft security products, Microsoft Threat Protection is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="fa34a-121">Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind.</span><span class="sxs-lookup"><span data-stu-id="fa34a-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="fa34a-122">Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fa34a-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="fa34a-123">Die Zeitleiste für Warnungen bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie in die Gründe, aus denen diese Warnungen mit diesem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="fa34a-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="fa34a-124">Und schließlich finden Sie im Abschnitt "Nachweise" eine Zusammenfassung der Anzahl der in den Vorfall einbezogenen Artefakte und ihres Behebungsstatus, sodass Sie sofort erkennen können, ob eine Maßnahme erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fa34a-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="fa34a-125">Diese Übersicht kann bei der ersten Analyse des Vorfalls hilfreich sein, indem sie einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.</span><span class="sxs-lookup"><span data-stu-id="fa34a-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="fa34a-126">Warnungen</span><span class="sxs-lookup"><span data-stu-id="fa34a-126">Alerts</span></span>

<span data-ttu-id="fa34a-127">Sie können alle Warnungen im Zusammenhang mit dem Vorfall und andere Informationen dazu anzeigen, z. B. den Schweregrad, die an der Warnung beteiligten Entitäten, die Quelle der Warnungen (Azure ATP, Microsoft Defender ATP, Office 365 ATP) und den Grund warum sie miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="fa34a-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Azure ATP, Microsoft Defender ATP , Office  365 ATP) and the reason they were linked together.</span></span>

![Abbildung der Seite mit Vorfallbenachrichtigungen](../../media/incident-alerts.png)

<span data-ttu-id="fa34a-129">Standardmäßig sind die Warnungen chronologisch geordnet, damit Sie zunächst sehen können, wie sich der Angriff im Laufe der Zeit abgespielt hat.</span><span class="sxs-lookup"><span data-stu-id="fa34a-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="fa34a-130">Wenn Sie auf jede Warnung klicken, gelangen Sie zu der entsprechenden Warnungsseite, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="fa34a-131">Geräte</span><span class="sxs-lookup"><span data-stu-id="fa34a-131">Devices</span></span>

<span data-ttu-id="fa34a-132">Auf der Registerkarte „Geräte“ werden alle Geräte aufgelistet, zu denen Warnungen bezüglich des Vorfalls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fa34a-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="fa34a-133">Wenn Sie auf den Namen des Rechners klicken, auf dem der Angriff ausgeführt wurde, gelangen Sie zur Seite "Rechner", auf der Sie Warnungen und verwandte Ereignisse zur Vereinfachung der Untersuchung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Abbildung der Registerkarte "Rechner" eines Vorfalls](../../media/incident-machines.png)

<span data-ttu-id="fa34a-135">Durch Auswahl der Registerkarte Zeitachse können Sie durch die Zeitachse der Rechner scrollen und alle Ereignisse und Verhaltensweisen, die auf dem Rechner beobachtet wurden, in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgegebenen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="fa34a-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="fa34a-136">Nutzer</span><span class="sxs-lookup"><span data-stu-id="fa34a-136">Users</span></span>

<span data-ttu-id="fa34a-137">Anzeigen von Nutzern, die als Bestandteil von oder mit einem bestimmten Vorfall verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="fa34a-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="fa34a-138">Durch Klicken auf den Nutzernamen gelangen Sie zur Cloud App Security-Seite des Nutzers, auf der weitere Untersuchungen durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Abbildung der Registerkarte "Nutzer" eines Vorfalls](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="fa34a-140">Postfächer</span><span class="sxs-lookup"><span data-stu-id="fa34a-140">Mailboxes</span></span>

<span data-ttu-id="fa34a-141">Untersuchen Sie Postfächer, bei denen festgestellt wurde, dass sie Teil eines Vorfalls sind oder sich auf einen Vorfall beziehen.</span><span class="sxs-lookup"><span data-stu-id="fa34a-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="fa34a-142">Wenn Sie die E-Mail-bezogene Warnung auswählen, um weitere Nachforschungen anzustellen, wird Office 365 Advanced Threat Protection geöffnet, in dem Sie Behebungsmaßnahmen ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-142">To do further investigative work, selecting the mail related alert will open Office 365 Advanced Threat Protection where you can take remediation actions.</span></span>

![Abbildung des Postfachregisters eines Vorfalls](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="fa34a-144">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="fa34a-144">Investigations</span></span>

<span data-ttu-id="fa34a-145">Wählen Sie unter **suchungen** aus, um alle automatisierten Untersuchungen anzuzeigen, die von Warnungen in diesem Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="fa34a-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="fa34a-146">Je nachdem, wie Sie Ihre automatisierten Untersuchungen für die Ausführung in Microsoft Defender ATP und Office 365 Advanced Threat Protection konfiguriert haben, führen die Untersuchungen Behebungsmaßnahmen durch oder warten auf die Genehmigung von Maßnahmen durch den Analysten.</span><span class="sxs-lookup"><span data-stu-id="fa34a-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender ATP and Office 365 Advanced Threat Protection.</span></span>

![Abbildung der Registerkarte "Untersuchungen“ eines Vorfalls](../../media/incident-investigations.png)

<span data-ttu-id="fa34a-148">Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="fa34a-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="fa34a-149">Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden diese auf der Registerkarte „Ausstehende Aktionen“ angezeigt. Ergreifen Sie Maßnahmen zur Behebung von Vorfällen.</span><span class="sxs-lookup"><span data-stu-id="fa34a-149">If there are any actions pending for approval as part of the investigation they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="fa34a-150">Beweis</span><span class="sxs-lookup"><span data-stu-id="fa34a-150">Evidence</span></span>

<span data-ttu-id="fa34a-151">Microsoft Threat Protection untersucht automatisch alle von Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und bietet Ihnen eine automatische Antwort sowie Informationen zu wichtigen Dateien, Prozessen, Diensten, E-Mails und vielem mehr.</span><span class="sxs-lookup"><span data-stu-id="fa34a-151">Microsoft Threat Protection automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with auto-response and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="fa34a-152">Dies hilft, potenzielle Bedrohungen im Vorfall schnell zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="fa34a-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Abbildung der Registerkarte "Beweise" eines Vorfalls](../../media/incident-evidence.png)

<span data-ttu-id="fa34a-154">Jede der analysierten Entitäten wird mit einem Urteil (Bösartig, Verdächtig, Sauber) sowie einem Behebungsstatus gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="fa34a-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="fa34a-155">Dies hilft Ihnen dabei, den Behebungsstatus des gesamten Vorfalls zu verstehen und zu ermitteln, welche weiteren Schritte zur Behebung des Vorfalls unternommen werden können.</span><span class="sxs-lookup"><span data-stu-id="fa34a-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa34a-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="fa34a-156">Related topics</span></span>

- [<span data-ttu-id="fa34a-157">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="fa34a-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="fa34a-158">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fa34a-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="fa34a-159">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="fa34a-159">Manage incidents</span></span>](manage-incidents.md)


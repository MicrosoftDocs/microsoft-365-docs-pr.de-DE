---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846748"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="84240-104">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84240-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="84240-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="84240-105">**Applies to:**</span></span>

- <span data-ttu-id="84240-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84240-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="84240-107">Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Beweise aus ihren Geräten, Benutzern und Postfächern, damit Sie einen umfassenden Einblick in die gesamte Bandbreite eines Angriffs erhalten.</span><span class="sxs-lookup"><span data-stu-id="84240-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="84240-108">Untersuchen Sie die Warnmeldungen, die Ihr Netzwerk betreffen, verstehen Sie, was sie bedeuten, und stellen Sie die mit den Vorfällen verbundenen Beweise zusammen, damit Sie einen wirksamen Plan zur Behebung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="84240-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="84240-109">Untersuchung eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="84240-109">Investigate an incident</span></span>

1. <span data-ttu-id="84240-110">Wählen Sie einen Vorfall aus der Vorfallwarteschlange aus.</span><span class="sxs-lookup"><span data-stu-id="84240-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="84240-111">Ein Seitenbereich wird geöffnet und zeigt eine Vorschau wichtiger Informationen wie Status, Schweregrad, Kategorien und betroffene Entitäten an.</span><span class="sxs-lookup"><span data-stu-id="84240-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild eines Seitenbereichs](../../media/incident-side-panel.png)

2. <span data-ttu-id="84240-113">Wählen Sie **Vorfallseite öffnen**.</span><span class="sxs-lookup"><span data-stu-id="84240-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="84240-114">Dadurch wird die Vorfall Seite geöffnet, auf der Sie weitere Informationen zu Vorfalldetails, Kommentaren und Aktionen, Registerkarten (Übersicht, Warnungen, Geräte, Benutzer, Untersuchungen, Beweise) finden.</span><span class="sxs-lookup"><span data-stu-id="84240-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="84240-115">Überprüfen Sie die Warnungen, Geräte, Nutzer und anderen Entitäten, die an dem Vorfall beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="84240-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="84240-116">Vorfall Übersicht</span><span class="sxs-lookup"><span data-stu-id="84240-116">Incident overview</span></span>

<span data-ttu-id="84240-117">Auf der Übersichtsseite erhalten Sie einen Überblick über die wichtigsten Informationen zu dem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="84240-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Abbildung der Vorfallübersichtsseite](../../media/incidents-overview.png)

<span data-ttu-id="84240-119">Die Angriffskategorien bieten eine visuelle und numerische Ansicht, wie fortgeschritten der Angriff für die killkette ist.</span><span class="sxs-lookup"><span data-stu-id="84240-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="84240-120">Wie bei anderen Microsoft-Sicherheitsprodukten wird Microsoft 365 Defender an das [Mitra ATT&CK &trade; ](https://attack.mitre.org/) -Framework angepasst.</span><span class="sxs-lookup"><span data-stu-id="84240-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="84240-121">Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind.</span><span class="sxs-lookup"><span data-stu-id="84240-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="84240-122">Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="84240-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="84240-123">Die Zeitleiste für Warnungen bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie in die Gründe, aus denen diese Warnungen mit diesem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="84240-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="84240-124">Und schließlich finden Sie im Abschnitt "Nachweise" eine Zusammenfassung der Anzahl der in den Vorfall einbezogenen Artefakte und ihres Behebungsstatus, sodass Sie sofort erkennen können, ob eine Maßnahme erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="84240-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="84240-125">Diese Übersicht kann bei der ersten Analyse des Vorfalls hilfreich sein, indem sie einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.</span><span class="sxs-lookup"><span data-stu-id="84240-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="84240-126">Warnungen</span><span class="sxs-lookup"><span data-stu-id="84240-126">Alerts</span></span>

<span data-ttu-id="84240-127">Sie können alle Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesen anzeigen, beispielsweise den Schweregrad, Entitäten, die an der Warnung beteiligt waren, die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender für Office 365) und den Grund, warum Sie miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="84240-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Abbildung der Seite mit Vorfallbenachrichtigungen](../../media/incident-alerts.png)

<span data-ttu-id="84240-129">Standardmäßig sind die Warnungen chronologisch geordnet, damit Sie zunächst sehen können, wie sich der Angriff im Laufe der Zeit abgespielt hat.</span><span class="sxs-lookup"><span data-stu-id="84240-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="84240-130">Durch Klicken auf jede Warnung gelangen Sie zur entsprechenden Benachrichtigungsseite, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können.</span><span class="sxs-lookup"><span data-stu-id="84240-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span>

## <a name="devices"></a><span data-ttu-id="84240-131">Geräte</span><span class="sxs-lookup"><span data-stu-id="84240-131">Devices</span></span>

<span data-ttu-id="84240-132">Auf der Registerkarte „Geräte“ werden alle Geräte aufgelistet, zu denen Warnungen bezüglich des Vorfalls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="84240-132">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="84240-133">Wenn Sie auf den Namen des Rechners klicken, auf dem der Angriff ausgeführt wurde, gelangen Sie zur Seite "Rechner", auf der Sie Warnungen und verwandte Ereignisse zur Vereinfachung der Untersuchung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="84240-133">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Abbildung der Registerkarte "Rechner" eines Vorfalls](../../media/incident-machines.png)

<span data-ttu-id="84240-135">Durch Auswahl der Registerkarte Zeitachse können Sie durch die Zeitachse der Rechner scrollen und alle Ereignisse und Verhaltensweisen, die auf dem Rechner beobachtet wurden, in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgegebenen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="84240-135">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

## <a name="users"></a><span data-ttu-id="84240-136">Nutzer</span><span class="sxs-lookup"><span data-stu-id="84240-136">Users</span></span>

<span data-ttu-id="84240-137">Anzeigen von Nutzern, die als Bestandteil von oder mit einem bestimmten Vorfall verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="84240-137">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="84240-138">Durch Klicken auf den Nutzernamen gelangen Sie zur Cloud App Security-Seite des Nutzers, auf der weitere Untersuchungen durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="84240-138">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Abbildung der Registerkarte "Nutzer" eines Vorfalls](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="84240-140">Postfächer</span><span class="sxs-lookup"><span data-stu-id="84240-140">Mailboxes</span></span>

<span data-ttu-id="84240-141">Untersuchen Sie Postfächer, bei denen festgestellt wurde, dass sie Teil eines Vorfalls sind oder sich auf einen Vorfall beziehen.</span><span class="sxs-lookup"><span data-stu-id="84240-141">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="84240-142">Für weitere Ermittlungsaufgaben wird durch Auswahl der e-Mail-bezogenen Warnung Microsoft Defender für Office 365 geöffnet, in dem Sie Korrekturaktionen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="84240-142">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Abbildung des Postfachregisters eines Vorfalls](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="84240-144">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="84240-144">Investigations</span></span>

<span data-ttu-id="84240-145">Wählen Sie unter **suchungen** aus, um alle automatisierten Untersuchungen anzuzeigen, die von Warnungen in diesem Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="84240-145">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="84240-146">In den Untersuchungen werden Korrekturaktionen durchgeführt oder auf die Analysten Genehmigung für Aktionen gewartet, je nachdem, wie Sie Ihre automatisierten Untersuchungen so konfiguriert haben, dass Sie in Microsoft Defender für Endpoint und Defender für Office 365 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="84240-146">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Abbildung der Registerkarte "Untersuchungen“ eines Vorfalls](../../media/incident-investigations.png)

<span data-ttu-id="84240-148">Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="84240-148">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="84240-149">Wenn im Rahmen der Untersuchung noch Aktionen zur Genehmigung ausstehen, werden diese auf der Registerkarte Ausstehende Aktionen angezeigt. Maßnahmen im Rahmen der Vorgehensweise bei der Problembehebung.</span><span class="sxs-lookup"><span data-stu-id="84240-149">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="84240-150">Beweis</span><span class="sxs-lookup"><span data-stu-id="84240-150">Evidence</span></span>

<span data-ttu-id="84240-151">Microsoft 365 Defender untersucht automatisch alle unterstützten Ereignisse der Vorfälle und verdächtigen Entitäten in den Warnungen und bietet Ihnen autoresponse und Informationen über wichtige Dateien, Prozesse, Dienste, e-Mails und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="84240-151">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="84240-152">Dies hilft, potenzielle Bedrohungen im Vorfall schnell zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="84240-152">This helps quickly detect and block potential threats in the incident.</span></span>

![Abbildung der Registerkarte "Beweise" eines Vorfalls](../../media/incident-evidence.png)

<span data-ttu-id="84240-154">Jede der analysierten Entitäten wird mit einem Urteil (Bösartig, Verdächtig, Sauber) sowie einem Behebungsstatus gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="84240-154">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="84240-155">Dies hilft Ihnen dabei, den Behebungsstatus des gesamten Vorfalls zu verstehen und zu ermitteln, welche weiteren Schritte zur Behebung des Vorfalls unternommen werden können.</span><span class="sxs-lookup"><span data-stu-id="84240-155">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84240-156">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="84240-156">Related topics</span></span>

- [<span data-ttu-id="84240-157">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="84240-157">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="84240-158">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="84240-158">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="84240-159">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="84240-159">Manage incidents</span></span>](manage-incidents.md)


---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
description: Analysieren Sie Vorfälle in Bezug auf Geräte, Nutzer und Postfächer.
keywords: Vorfall, Vorfälle, Rechner, Geräte, Nutzer, Identitäten, Post, E-Mail, Postfach, Untersuchung, Graph, Beweise
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
ms.openlocfilehash: a6c7e7e920d18d9d8bf29d71d317008ea0c37bbf
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592096"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="1f504-104">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f504-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="1f504-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1f504-105">**Applies to:**</span></span>

- <span data-ttu-id="1f504-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f504-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="1f504-107">Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Nachweise auf Allen Geräten, Benutzern und Postfächern, um Ihnen einen umfassenden Einblick in die gesamte Bandbreite eines Angriffs zu bieten.</span><span class="sxs-lookup"><span data-stu-id="1f504-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations and evidence from across your devices, users, and mailboxes to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="1f504-108">Untersuchen Sie die Warnmeldungen, die Ihr Netzwerk betreffen, verstehen Sie, was sie bedeuten, und stellen Sie die mit den Vorfällen verbundenen Beweise zusammen, damit Sie einen wirksamen Plan zur Behebung erstellen können.</span><span class="sxs-lookup"><span data-stu-id="1f504-108">Investigate the alerts that affect your network, understand what they mean, and collate evidence associated with the incidents so that you can devise an effective remediation plan.</span></span>

## <a name="investigate-an-incident"></a><span data-ttu-id="1f504-109">Untersuchung eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="1f504-109">Investigate an incident</span></span>

1. <span data-ttu-id="1f504-110">Wählen Sie einen Vorfall aus der Vorfallwarteschlange aus.</span><span class="sxs-lookup"><span data-stu-id="1f504-110">Select an incident from the incident queue.</span></span> <BR> <span data-ttu-id="1f504-111">Ein Seitenbereich wird geöffnet und bietet eine Vorschau wichtiger Informationen wie Status, Schweregrad, Kategorien und die betroffen Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1f504-111">A side panel opens and gives a preview of important information such as status, severity, categories, and the impacted entities.</span></span>

    ![Bild eines Seitenbereichs](../../media/incident-side-panel.png)

2. <span data-ttu-id="1f504-113">Wählen Sie **Vorfallseite öffnen**.</span><span class="sxs-lookup"><span data-stu-id="1f504-113">Select **Open incident page**.</span></span> <BR> <span data-ttu-id="1f504-114">Dadurch wird die Vorfallseite geöffnet, auf der Sie weitere Informationen zu Vorfällen, Kommentaren und Aktionen, Registerkarten (Übersicht, Warnungen, Geräte, Benutzer, Untersuchungen, Nachweise) finden.</span><span class="sxs-lookup"><span data-stu-id="1f504-114">This opens the incident page where you'll find more information incident details, comments, and actions, tabs (overview, alerts, devices, users, investigations, evidence).</span></span>

3. <span data-ttu-id="1f504-115">Überprüfen Sie die Warnungen, Geräte, Nutzer und anderen Entitäten, die an dem Vorfall beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="1f504-115">Review the alerts, devices, users, other entities involved in the incident.</span></span>

## <a name="incident-overview"></a><span data-ttu-id="1f504-116">Vorfall Übersicht</span><span class="sxs-lookup"><span data-stu-id="1f504-116">Incident overview</span></span>

<span data-ttu-id="1f504-117">Auf der Übersichtsseite erhalten Sie einen Überblick über die wichtigsten Informationen zu dem Vorfall.</span><span class="sxs-lookup"><span data-stu-id="1f504-117">The overview page gives you a snapshot glance into the top things to notice about the incident.</span></span>

![Abbildung der Vorfallübersichtsseite](../../media/incidents-overview.png)

<span data-ttu-id="1f504-119">Die Angriffskategorien bieten Ihnen eine visuelle und numerische Ansicht, wie weit der Angriff gegenüber der Kill Chain fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="1f504-119">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="1f504-120">Wie bei anderen Microsoft-Sicherheitsprodukten ist Microsoft 365 Defender am [MITRE &trade; ATT-&CK-Framework](https://attack.mitre.org/) ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="1f504-120">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="1f504-121">Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind.</span><span class="sxs-lookup"><span data-stu-id="1f504-121">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="1f504-122">Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f504-122">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="1f504-123">Die Zeitleiste für Warnungen bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie in die Gründe, aus denen diese Warnungen mit diesem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="1f504-123">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts linked to this incident.</span></span>

<span data-ttu-id="1f504-124">Und schließlich finden Sie im Abschnitt "Nachweise" eine Zusammenfassung der Anzahl der in den Vorfall einbezogenen Artefakte und ihres Behebungsstatus, sodass Sie sofort erkennen können, ob eine Maßnahme erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1f504-124">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed on your end.</span></span>

<span data-ttu-id="1f504-125">Diese Übersicht kann bei der ersten Analyse des Vorfalls hilfreich sein, indem sie einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.</span><span class="sxs-lookup"><span data-stu-id="1f504-125">This overview can assist in the initial triage of the incident by providing insight to the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="1f504-126">Warnungen</span><span class="sxs-lookup"><span data-stu-id="1f504-126">Alerts</span></span>

<span data-ttu-id="1f504-127">Sie können alle Warnungen im Zusammenhang mit dem Vorfall und andere Informationen dazu anzeigen, z. B. schweregrad, Entitäten, die an der Warnung beteiligt waren, die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender für Office 365) und den Grund, warum sie miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="1f504-127">You can view all the alerts related to the incident and other information about them such as severity, entities that were involved in the alert, the source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365) and the reason they were linked together.</span></span>

![Abbildung der Seite mit Vorfallbenachrichtigungen](../../media/incident-alerts.png)

<span data-ttu-id="1f504-129">Standardmäßig sind die Warnungen chronologisch geordnet, damit Sie zunächst sehen können, wie sich der Angriff im Laufe der Zeit abgespielt hat.</span><span class="sxs-lookup"><span data-stu-id="1f504-129">By default, the alerts are ordered chronologically, to allow you to first view how the attack played out over time.</span></span> <span data-ttu-id="1f504-130">Wenn Sie auf jede Warnung klicken, gelangen Sie zur entsprechenden Warnungsseite, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können.</span><span class="sxs-lookup"><span data-stu-id="1f504-130">Clicking on each alert will lead you to the relevant alert page where you can conduct an in-depth investigation of that alert.</span></span> <span data-ttu-id="1f504-131">Informationen zur Verwendung von Warnungsseiten und der einheitlichen Warnungswarteschlange unter [Warnungen untersuchen](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="1f504-131">Learn how to use alert pages and the unified alert queue in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="1f504-132">Geräte</span><span class="sxs-lookup"><span data-stu-id="1f504-132">Devices</span></span>

<span data-ttu-id="1f504-133">Auf der Registerkarte „Geräte“ werden alle Geräte aufgelistet, zu denen Warnungen bezüglich des Vorfalls angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f504-133">The devices tab lists all the devices where alerts related to the incident are seen.</span></span>

<span data-ttu-id="1f504-134">Wenn Sie auf den Namen des Rechners klicken, auf dem der Angriff ausgeführt wurde, gelangen Sie zur Seite "Rechner", auf der Sie Warnungen und verwandte Ereignisse zur Vereinfachung der Untersuchung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="1f504-134">Clicking the name of the machine where the attack was conducted navigates you to its Machine page where you can see alerts that were triggered on it and related events provided to ease investigation.</span></span>

![Abbildung der Registerkarte "Rechner" eines Vorfalls](../../media/incident-machines.png)

<span data-ttu-id="1f504-136">Durch Auswahl der Registerkarte Zeitachse können Sie durch die Zeitachse der Rechner scrollen und alle Ereignisse und Verhaltensweisen, die auf dem Rechner beobachtet wurden, in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgegebenen Warnungen.</span><span class="sxs-lookup"><span data-stu-id="1f504-136">Selecting the Timeline tab enables you to scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="1f504-137">Sie können Bedarfsscans auf einer Geräteseite durchführen.</span><span class="sxs-lookup"><span data-stu-id="1f504-137">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="1f504-138">Wählen Sie im Microsoft 365 Security Center **Gerätebestand aus.**</span><span class="sxs-lookup"><span data-stu-id="1f504-138">In the Microsoft 365 security center, choose **Device inventory**.</span></span> <span data-ttu-id="1f504-139">Wählen Sie ein Gerät mit Warnungen aus, und führen Sie dann eine Antivirenscan aus.</span><span class="sxs-lookup"><span data-stu-id="1f504-139">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="1f504-140">Aktionen, z. B. Antivirenscans, werden nachverfolgt und sind auf der Seite **Geräteinventar** sichtbar.</span><span class="sxs-lookup"><span data-stu-id="1f504-140">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="1f504-141">Weitere Informationen finden Sie unter [Ausführen der Microsoft Defender Antivirus-Überprüfung auf Geräten](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="1f504-141">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>


## <a name="users"></a><span data-ttu-id="1f504-142">Nutzer</span><span class="sxs-lookup"><span data-stu-id="1f504-142">Users</span></span>

<span data-ttu-id="1f504-143">Anzeigen von Nutzern, die als Bestandteil von oder mit einem bestimmten Vorfall verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="1f504-143">See users that have been identified to be part of, or related to a given incident.</span></span>

<span data-ttu-id="1f504-144">Durch Klicken auf den Nutzernamen gelangen Sie zur Cloud App Security-Seite des Nutzers, auf der weitere Untersuchungen durchgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="1f504-144">Clicking the username navigates you to the user's Cloud App Security page where further investigation can be conducted.</span></span>

![Abbildung der Registerkarte "Nutzer" eines Vorfalls](../../media/incident-users.png)

## <a name="mailboxes"></a><span data-ttu-id="1f504-146">Postfächer</span><span class="sxs-lookup"><span data-stu-id="1f504-146">Mailboxes</span></span>

<span data-ttu-id="1f504-147">Untersuchen Sie Postfächer, bei denen festgestellt wurde, dass sie Teil eines Vorfalls sind oder sich auf einen Vorfall beziehen.</span><span class="sxs-lookup"><span data-stu-id="1f504-147">Investigate mailboxes that's been identified to be part of, or related to an incident.</span></span> <span data-ttu-id="1f504-148">Um weitere Ermittlungen zu ergreifen, wird microsoft Defender for Office 365 geöffnet, indem Sie die E-Mail-bezogene Warnung auswählen, wo Sie Abhilfemaßnahmen ausführen können.</span><span class="sxs-lookup"><span data-stu-id="1f504-148">To do further investigative work, selecting the mail-related alert will open Microsoft Defender for Office 365 where you can take remediation actions.</span></span>

![Abbildung des Postfachregisters eines Vorfalls](../../media/incident-mailboxes.png)

## <a name="investigations"></a><span data-ttu-id="1f504-150">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1f504-150">Investigations</span></span>

<span data-ttu-id="1f504-151">Wählen **Sie Untersuchungen** aus, um alle automatisierten Untersuchungen anzuzeigen, die durch Warnungen in diesem Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1f504-151">Select **Investigations** to see all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="1f504-152">Die Untersuchungen führen Korrekturmaßnahmen durch oder warten auf die Genehmigung von Aktionen durch Analysten, je nachdem, wie Sie Ihre automatisierten Untersuchungen für die Ausführung in Microsoft Defender for Endpoint und Defender für Office 365 konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1f504-152">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

![Abbildung der Registerkarte "Untersuchungen“ eines Vorfalls](../../media/incident-investigations.png)

<span data-ttu-id="1f504-154">Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f504-154">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="1f504-155">Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden sie auf der Registerkarte Ausstehende Aktionen angezeigt. Ergreifen Sie Maßnahmen im Rahmen der Vorfallbehebung.</span><span class="sxs-lookup"><span data-stu-id="1f504-155">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence"></a><span data-ttu-id="1f504-156">Beweis</span><span class="sxs-lookup"><span data-stu-id="1f504-156">Evidence</span></span>

<span data-ttu-id="1f504-157">Microsoft 365 Defender untersucht automatisch alle von Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Autoresponse und Informationen zu wichtigen Dateien, Prozessen, Diensten, E-Mails und mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1f504-157">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, emails, and more.</span></span> <span data-ttu-id="1f504-158">Dies hilft, potenzielle Bedrohungen im Vorfall schnell zu erkennen und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="1f504-158">This helps quickly detect and block potential threats in the incident.</span></span>

![Abbildung der Registerkarte "Beweise" eines Vorfalls](../../media/incident-evidence.png)

<span data-ttu-id="1f504-160">Jede der analysierten Entitäten wird mit einem Urteil (Bösartig, Verdächtig, Sauber) sowie einem Behebungsstatus gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="1f504-160">Each of the analyzed entities will be marked with a verdict (Malicious, Suspicious, Clean) as well as a remediation status.</span></span> <span data-ttu-id="1f504-161">Dies hilft Ihnen dabei, den Behebungsstatus des gesamten Vorfalls zu verstehen und zu ermitteln, welche weiteren Schritte zur Behebung des Vorfalls unternommen werden können.</span><span class="sxs-lookup"><span data-stu-id="1f504-161">This assists you in understanding the remediation status of the entire incident and what are the next steps that can be taken to further remediate.</span></span>

## <a name="related-topics"></a><span data-ttu-id="1f504-162">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1f504-162">Related topics</span></span>

- [<span data-ttu-id="1f504-163">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="1f504-163">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="1f504-164">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="1f504-164">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="1f504-165">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="1f504-165">Manage incidents</span></span>](manage-incidents.md)


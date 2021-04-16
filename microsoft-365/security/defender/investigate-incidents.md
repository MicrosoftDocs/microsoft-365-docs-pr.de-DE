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
ms.openlocfilehash: 99acc25c3949b758dab990a9c2e9104b9158accd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861875"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d466c-104">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d466c-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d466c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d466c-105">**Applies to:**</span></span>

- <span data-ttu-id="d466c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d466c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="d466c-107">Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Nachweise aus Ihren Geräten, Benutzern und Postfächern in einem Vorfall, um Ihnen einen umfassenden Überblick über die gesamte Bandbreite eines Angriffs zu geben.</span><span class="sxs-lookup"><span data-stu-id="d466c-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="d466c-108">Innerhalb eines Vorfalls untersuchen Sie die Warnungen, die sich auf Ihr Netzwerk auswirken, verstehen, was sie bedeuten, und erstellen die Nachweise, damit Sie einen effektiven Korrekturplan entwickeln können.</span><span class="sxs-lookup"><span data-stu-id="d466c-108">Within an incident, you investigate the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="d466c-109">Erste Untersuchung</span><span class="sxs-lookup"><span data-stu-id="d466c-109">Initial investigation</span></span>

<span data-ttu-id="d466c-110">Bevor Sie in die Details eintauchen, sehen Sie sich die Eigenschaften und die Zusammenfassung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="d466c-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="d466c-111">Sie können beginnen, indem Sie den Vorfall in der Häkchenspalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="d466c-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="d466c-112">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Beispiel für die Auswahl eines Vorfalls aus der Häkchenspalte":::

<span data-ttu-id="d466c-114">In diesem Fall wird ein Zusammenfassungsbereich mit wichtigen Informationen zum Vorfall geöffnet, z. B. schweregrad, wem er zugewiesen ist, und die [MITRE ATT-&&trade; CK-Kategorien](https://attack.mitre.org/) für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="d466c-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="d466c-115">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Beispiel für den Zusammenfassungsbereich für einen Vorfall":::

<span data-ttu-id="d466c-117">Hier können Sie die Seite **"Vorfall öffnen" auswählen.**</span><span class="sxs-lookup"><span data-stu-id="d466c-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="d466c-118">Dadurch wird die Hauptseite für den Vorfall geöffnet, auf der Sie weitere Zusammenfassungsinformationen und Registerkarten für Warnungen, Geräte, Benutzer, Untersuchungen und Nachweise finden.</span><span class="sxs-lookup"><span data-stu-id="d466c-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="d466c-119">Sie können auch die Hauptseite für einen Vorfall öffnen, indem Sie den Vorfallnamen aus der Vorfallwarteschlange auswählen.</span><span class="sxs-lookup"><span data-stu-id="d466c-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="d466c-120">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d466c-120">Summary</span></span>

<span data-ttu-id="d466c-121">Auf **der** Seite Zusammenfassung finden Sie einen Überblick über die wichtigsten Dinge, die Sie über den Vorfall bemerken können.</span><span class="sxs-lookup"><span data-stu-id="d466c-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Zusammenfassungsseite für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="d466c-123">Die Angriffskategorien bieten Ihnen eine visuelle und numerische Ansicht, wie weit der Angriff gegenüber der Kill Chain fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="d466c-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="d466c-124">Wie bei anderen Microsoft-Sicherheitsprodukten ist Microsoft 365 Defender am [MITRE &trade; ATT-&CK-Framework](https://attack.mitre.org/) ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d466c-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="d466c-125">Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind.</span><span class="sxs-lookup"><span data-stu-id="d466c-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="d466c-126">Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d466c-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="d466c-127">Die Zeitachse für Warnungen bietet einen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie die Gründe, warum diese Warnungen mit diesem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="d466c-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="d466c-128">Und last – der Abschnitt "Evidence" enthält eine Zusammenfassung der Anzahl der verschiedenen Artefakte, die in den Vorfall einbezogen wurden, und deren Behebungsstatus, damit Sie sofort erkennen können, ob eine Aktion von Ihnen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d466c-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="d466c-129">Diese Übersicht kann bei der anfänglichen Triage des Vorfalls helfen, indem sie Einen Einblick in die wichtigsten Merkmale des Vorfalls bietet, die Sie beachten sollten.</span><span class="sxs-lookup"><span data-stu-id="d466c-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="d466c-130">Warnungen</span><span class="sxs-lookup"><span data-stu-id="d466c-130">Alerts</span></span>

<span data-ttu-id="d466c-131">Auf der **Registerkarte Warnung** können Sie die Warnwarteschlange für Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesem Ereignis anzeigen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="d466c-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="d466c-132">Schweregrad.</span><span class="sxs-lookup"><span data-stu-id="d466c-132">Severity.</span></span>
- <span data-ttu-id="d466c-133">Die Entitäten, die an der Warnung beteiligt waren.</span><span class="sxs-lookup"><span data-stu-id="d466c-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="d466c-134">Die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="d466c-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="d466c-135">Der Grund, warum sie miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="d466c-135">The reason they were linked together.</span></span>

<span data-ttu-id="d466c-136">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Beispiel für eine Warnungsseite für einen Vorfall":::

<span data-ttu-id="d466c-138">Standardmäßig werden die Warnungen chronologisch geordnet, damit Sie sehen können, wie sich der Vorfall im Laufe der Zeit abgespielt hat.</span><span class="sxs-lookup"><span data-stu-id="d466c-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="d466c-139">Wenn Sie jede Warnung auswählen, gelangen Sie zur Hauptseite der Warnung, auf der Sie eine eingehende Untersuchung dieser Warnung durchführen können.</span><span class="sxs-lookup"><span data-stu-id="d466c-139">Selecting each alert takes you to the alert's main page where you can conduct an in-depth investigation of that alert.</span></span> 

<span data-ttu-id="d466c-140">Informationen zur Verwendung der Warnungswarteschlange und der Warnungsseiten unter [Warnungen untersuchen](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="d466c-140">Learn how to use the alert queue and alert pages in [Investigate alerts](investigate-alerts.md)</span></span>

## <a name="devices"></a><span data-ttu-id="d466c-141">Geräte</span><span class="sxs-lookup"><span data-stu-id="d466c-141">Devices</span></span>

<span data-ttu-id="d466c-142">Auf **der** Registerkarte Geräte werden alle Geräte im Zusammenhang mit dem Vorfall aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="d466c-142">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="d466c-143">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-143">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Beispiel für eine Geräteseite für einen Vorfall":::

<span data-ttu-id="d466c-145">Sie können das Häkchen für ein Gerät aktivieren, um Details zu Gerät, Verzeichnisdaten, aktiven Warnungen und angemeldeten Benutzern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-145">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="d466c-146">Wählen Sie den Namen des Geräts aus, um Gerätedetails im Microsoft Defender for Endpoints-Gerätebestand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-146">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Beispiel für eine Geräteseite für Microsoft Defender for Endpoints":::

<span data-ttu-id="d466c-148">Auf der Geräteseite können Sie zusätzliche Informationen zum Gerät sammeln, z. B. alle Warnungen, eine Zeitachse und Sicherheitsempfehlungen.</span><span class="sxs-lookup"><span data-stu-id="d466c-148">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="d466c-149">Auf der Registerkarte  Zeitachse können Sie beispielsweise einen Bildlauf durch die Zeitachse des Computers durchführen und alle auf dem Computer beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzeigen, die durch die ausgelösten Warnungen durchgezogen sind.</span><span class="sxs-lookup"><span data-stu-id="d466c-149">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="d466c-150">Sie können Bedarfsscans auf einer Geräteseite durchführen.</span><span class="sxs-lookup"><span data-stu-id="d466c-150">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="d466c-151">Wählen Sie im Microsoft 365 Security Center **Endpunkte > Gerätebestand aus.**</span><span class="sxs-lookup"><span data-stu-id="d466c-151">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="d466c-152">Wählen Sie ein Gerät mit Warnungen aus, und führen Sie dann eine Antivirenscan aus.</span><span class="sxs-lookup"><span data-stu-id="d466c-152">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="d466c-153">Aktionen, z. B. Antivirenscans, werden nachverfolgt und sind auf der Seite **Geräteinventar** sichtbar.</span><span class="sxs-lookup"><span data-stu-id="d466c-153">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="d466c-154">Weitere Informationen finden Sie unter [Ausführen der Microsoft Defender Antivirus-Überprüfung auf Geräten](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span><span class="sxs-lookup"><span data-stu-id="d466c-154">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="d466c-155">Benutzer</span><span class="sxs-lookup"><span data-stu-id="d466c-155">Users</span></span>

<span data-ttu-id="d466c-156">Auf **der** Registerkarte Benutzer werden alle Benutzer aufgeführt, die als Teil oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="d466c-156">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="d466c-157">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-157">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel einer Benutzerseite für einen Vorfall":::

<span data-ttu-id="d466c-159">Sie können das Häkchen für einen Benutzer aktivieren, um Details zur Bedrohung, Belichtung und Kontaktinformationen des Benutzerkontos anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-159">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="d466c-160">Wählen Sie den Benutzernamen aus, um weitere Benutzerkontodetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-160">Select the user name to see additional user account details.</span></span>

## <a name="mailboxes"></a><span data-ttu-id="d466c-161">Postfächer</span><span class="sxs-lookup"><span data-stu-id="d466c-161">Mailboxes</span></span>

<span data-ttu-id="d466c-162">Auf **der Registerkarte** Postfächer werden alle Postfächer aufgeführt, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="d466c-162">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="d466c-163">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-163">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Beispiel einer Postfachseite für einen Vorfall":::

<span data-ttu-id="d466c-165">Sie können das Häkchen für ein Postfach aktivieren, um eine Liste aktiver Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-165">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="d466c-166">Wählen Sie den Postfachnamen aus, um zusätzliche Postfachdetails auf der Explorer-Seite für Microsoft Defender für Office 365 anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d466c-166">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="d466c-167">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="d466c-167">Investigations</span></span>

<span data-ttu-id="d466c-168">Auf **der Registerkarte** Untersuchungen sind alle automatisierten Untersuchungen aufgeführt, die durch Warnungen in diesem Vorfall ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="d466c-168">The **Investigations** tab lists all the automated investigations triggered by alerts in this incident.</span></span> <span data-ttu-id="d466c-169">Die Untersuchungen führen Korrekturmaßnahmen durch oder warten auf die Genehmigung von Aktionen durch Analysten, je nachdem, wie Sie Ihre automatisierten Untersuchungen für die Ausführung in Microsoft Defender for Endpoint und Defender für Office 365 konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="d466c-169">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Beispiel für eine Seite &quot;Untersuchungen&quot; für einen Vorfall":::

<span data-ttu-id="d466c-171">Wählen Sie eine Untersuchung aus, um zur Seite mit den Untersuchungsdetails zu navigieren und vollständige Informationen zum Untersuchungs- und Behebungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d466c-171">Select an investigation to navigate to the Investigation details page to get full information on the investigation and remediation status.</span></span> <span data-ttu-id="d466c-172">Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden sie auf der Registerkarte Ausstehende Aktionen angezeigt. Ergreifen Sie Maßnahmen im Rahmen der Vorfallbehebung.</span><span class="sxs-lookup"><span data-stu-id="d466c-172">If there are any actions pending for approval as part of the investigation, they will appear in the Pending actions tab. Take action as part of incident remediation.</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="d466c-173">Nachweis und Antwort</span><span class="sxs-lookup"><span data-stu-id="d466c-173">Evidence and Response</span></span>

<span data-ttu-id="d466c-174">Auf **der Registerkarte Nachweis und Antwort** werden alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen im Vorfall angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d466c-174">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="d466c-175">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="d466c-175">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Beispiel für eine Evidenz- und Reaktionsseite für einen Vorfall":::

<span data-ttu-id="d466c-177">Microsoft 365 Defender untersucht automatisch alle von Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Informationen zu wichtigen E-Mails, Dateien, Prozessen, Diensten, IP-Adressen und mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="d466c-177">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="d466c-178">Auf diese Weise können Sie potenzielle Bedrohungen in dem Vorfall schnell erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="d466c-178">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="d466c-179">Jede der analysierten Entitäten ist mit einem Urteil (Bösartig, Verdächtig, Clean) und einem Behebungsstatus gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d466c-179">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="d466c-180">Auf diese Weise können Sie den Behebungsstatus des gesamten Vorfalls und die nächsten Schritte verstehen.</span><span class="sxs-lookup"><span data-stu-id="d466c-180">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d466c-181">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d466c-181">Related topics</span></span>

- [<span data-ttu-id="d466c-182">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="d466c-182">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="d466c-183">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d466c-183">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="d466c-184">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="d466c-184">Manage incidents</span></span>](manage-incidents.md)


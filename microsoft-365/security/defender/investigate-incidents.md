---
title: Untersuchen von Vorfällen in Microsoft 365 Defender
description: Untersuchen sie Vorfälle im Zusammenhang mit Geräten, Benutzern und Postfächern.
keywords: Incident, incidents, analyze, response, machines, devices, users, identities, mail, email, mailbox, investigation, graph, evidence
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
- incidentresponse
- m365solution-incidentresponse
- m365solution-overview
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fdfc065aea3549e99de72c968c0fa19412f9e246
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105356"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a><span data-ttu-id="68004-104">Untersuchen von Vorfällen in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68004-104">Investigate incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="68004-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="68004-105">**Applies to:**</span></span>

- <span data-ttu-id="68004-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68004-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="68004-107">Microsoft 365 Defender aggregiert alle zugehörigen Warnungen, Ressourcen, Untersuchungen und Nachweise aus Ihren Geräten, Benutzern und Postfächern zu einem Vorfall, um Ihnen einen umfassenden Überblick über die gesamte Breite eines Angriffs zu geben.</span><span class="sxs-lookup"><span data-stu-id="68004-107">Microsoft 365 Defender aggregates all related alerts, assets, investigations, and evidence from across your devices, users, and mailboxes into an incident to give you a comprehensive look into the entire breadth of an attack.</span></span>

<span data-ttu-id="68004-108">Innerhalb eines Vorfalls analysieren Sie die Warnungen, die sich auf Ihr Netzwerk auswirken, verstehen, was sie bedeuten, und sortieren die Nachweise, damit Sie einen effektiven Korrekturplan erstellen können.</span><span class="sxs-lookup"><span data-stu-id="68004-108">Within an incident, you analyze the alerts that affect your network, understand what they mean, and collate the evidence so that you can devise an effective remediation plan.</span></span>

## <a name="initial-investigation"></a><span data-ttu-id="68004-109">Anfängliche Untersuchung</span><span class="sxs-lookup"><span data-stu-id="68004-109">Initial investigation</span></span>

<span data-ttu-id="68004-110">Bevor Sie sich mit den Details befassen, sehen Sie sich die Eigenschaften und die Zusammenfassung des Vorfalls an.</span><span class="sxs-lookup"><span data-stu-id="68004-110">Before diving into the details, take a look at the properties and summary of the incident.</span></span>

<span data-ttu-id="68004-111">Sie können beginnen, indem Sie den Vorfall in der Häkchenspalte auswählen.</span><span class="sxs-lookup"><span data-stu-id="68004-111">You can start by selecting the incident from the check mark column.</span></span> <span data-ttu-id="68004-112">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-112">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Beispiel für die Auswahl eines Vorfalls in der Häkchenspalte":::

<span data-ttu-id="68004-114">In diesem Fall wird ein Zusammenfassungsbereich mit wichtigen Informationen zu dem Vorfall geöffnet, z. B. dem Schweregrad, dem er zugewiesen ist, und dem [MITRE ATT&&trade; CK-Kategorien](https://attack.mitre.org/) für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="68004-114">When you do, a summary pane opens with key information about the incident, such as severity, to whom it is assigned, and the [MITRE ATT&CK&trade;](https://attack.mitre.org/) categories for the incident.</span></span> <span data-ttu-id="68004-115">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-115">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Beispiel für den Zusammenfassungsbereich für einen Vorfall":::

<span data-ttu-id="68004-117">Von hier aus können Sie die **Seite "Vorfall öffnen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="68004-117">From here, you can select **Open incident page**.</span></span> <span data-ttu-id="68004-118">Dadurch wird die Hauptseite für den Vorfall geöffnet, auf der Sie weitere zusammenfassende Informationen und Registerkarten für Warnungen, Geräte, Benutzer, Untersuchungen und Nachweise finden.</span><span class="sxs-lookup"><span data-stu-id="68004-118">This opens the main page for the incident where you'll find more summary information and tabs for alerts, devices, users, investigations, and evidence.</span></span>

<span data-ttu-id="68004-119">Sie können auch die Hauptseite für einen Vorfall öffnen, indem Sie den Namen des Vorfalls aus der Vorfallwarteschlange auswählen.</span><span class="sxs-lookup"><span data-stu-id="68004-119">You can also open the main page for an incident by selecting the incident name from the incident queue.</span></span>

## <a name="summary"></a><span data-ttu-id="68004-120">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="68004-120">Summary</span></span>

<span data-ttu-id="68004-121">Auf der **Zusammenfassungsseite** erhalten Sie einen Momentaufnahme-Blick auf die wichtigsten Punkte, die Sie über den Vorfall feststellen können.</span><span class="sxs-lookup"><span data-stu-id="68004-121">The **Summary** page gives you a snapshot glance at the top things to notice about the incident.</span></span>

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Beispiel für die Seite &quot;Zusammenfassung&quot; für einen Vorfall im Microsoft 365 Security Center":::

<span data-ttu-id="68004-123">Die Angriffskategorien geben Ihnen eine visuelle und numerische Übersicht darüber, wie fortgeschritten der Angriff gegen die Kill Chain fortgeschritten ist.</span><span class="sxs-lookup"><span data-stu-id="68004-123">The attack categories give you a visual and numeric view of how advanced the attack has progressed against the kill chain.</span></span> <span data-ttu-id="68004-124">Wie bei anderen Microsoft-Sicherheitsprodukten ist Microsoft 365 Defender auf das [MITRE ATT &trade;&CK-Framework](https://attack.mitre.org/) ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="68004-124">As with other Microsoft security products, Microsoft 365 Defender is aligned to the [MITRE ATT&CK&trade;](https://attack.mitre.org/) framework.</span></span>

<span data-ttu-id="68004-125">Der Bereich enthält eine Liste der am häufigsten betroffenen Assets, die Teil dieses Vorfalls sind.</span><span class="sxs-lookup"><span data-stu-id="68004-125">The scope section gives you a list of top impacted assets that are part of this incident.</span></span> <span data-ttu-id="68004-126">Wenn es spezifische Informationen zu diesem Asset gibt, wie z. B. Risikograd, Untersuchungspriorität sowie eine Kennzeichnung des Assets, wird dies ebenfalls in diesem Abschnitt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68004-126">If there is specific information regarding this asset, such as risk level, investigation priority as well as any tagging on the assets this will also surface in this section.</span></span>

<span data-ttu-id="68004-127">Die Warnungszeitachse bietet einen kurzen Einblick in die chronologische Reihenfolge, in der die Warnungen aufgetreten sind, sowie die Gründe, warum diese Warnungen mit diesem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="68004-127">The alerts timeline provides a sneak peek into the chronological order in which the alerts occurred, as well as the reasons that these alerts are linked to this incident.</span></span>

<span data-ttu-id="68004-128">Und schließlich – der Nachweisabschnitt enthält eine Zusammenfassung der Anzahl der verschiedenen Artefakte, die in den Vorfall einbezogen wurden, und deren Behebungsstatus, sodass Sie sofort erkennen können, ob eine Aktion von Ihnen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="68004-128">And last - the evidence section provides a summary of how many different artifacts were included in the incident and their remediation status, so you can immediately identify if any action is needed by you.</span></span>

<span data-ttu-id="68004-129">Diese Übersicht kann Ihnen bei der anfänglichen Triage des Vorfalls helfen, indem sie Einblicke in die wichtigsten Merkmale des Vorfalls bietet, die Sie kennen sollten.</span><span class="sxs-lookup"><span data-stu-id="68004-129">This overview can assist in the initial triage of the incident by providing insight into the top characteristics of the incident that you should be aware of.</span></span>

## <a name="alerts"></a><span data-ttu-id="68004-130">Warnungen</span><span class="sxs-lookup"><span data-stu-id="68004-130">Alerts</span></span>

<span data-ttu-id="68004-131">Auf der Registerkarte **"Warnung"** können Sie die Warnungswarteschlange für Warnungen im Zusammenhang mit dem Vorfall und andere Informationen zu diesen anzeigen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="68004-131">On the **Alert** tab, you can view the alert queue for alerts related to the incident and other information about them such as:</span></span>

- <span data-ttu-id="68004-132">Schweregrad.</span><span class="sxs-lookup"><span data-stu-id="68004-132">Severity.</span></span>
- <span data-ttu-id="68004-133">Die Entitäten, die an der Warnung beteiligt waren.</span><span class="sxs-lookup"><span data-stu-id="68004-133">The entities that were involved in the alert.</span></span>
- <span data-ttu-id="68004-134">Die Quelle der Warnungen (Microsoft Defender for Identity, Microsoft Defender für Endpunkt, Microsoft Defender für Office 365).</span><span class="sxs-lookup"><span data-stu-id="68004-134">The source of the alerts (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender for Office 365).</span></span>
- <span data-ttu-id="68004-135">Der Grund, warum sie miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="68004-135">The reason they were linked together.</span></span>

<span data-ttu-id="68004-136">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-136">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Beispiel für eine Seite &quot;Warnungen&quot; für einen Vorfall":::

<span data-ttu-id="68004-138">Standardmäßig sind die Warnungen chronologisch sortiert, damit Sie sehen können, wie der Vorfall im Laufe der Zeit ausgespielt wurde.</span><span class="sxs-lookup"><span data-stu-id="68004-138">By default, the alerts are ordered chronologically to allow you to see how the incident played out over time.</span></span> <span data-ttu-id="68004-139">Wenn Sie eine Warnung innerhalb eines Vorfalls auswählen, zeigt Microsoft 365 Defender die spezifischen Warnungsinformationen für den Kontext des Gesamtvorfalls an.</span><span class="sxs-lookup"><span data-stu-id="68004-139">When you select an alert within an incident, Microsoft 365 Defender displays the alert information specific to the context of the overall incident.</span></span> 

<span data-ttu-id="68004-140">Sie können die Ereignisse der Warnung sehen, durch die andere ausgelöste Warnungen die aktuelle Warnung verursacht haben, sowie alle betroffenen Entitäten und Aktivitäten, die an dem Angriff beteiligt sind, einschließlich Dateien, Benutzern und Postfächern.</span><span class="sxs-lookup"><span data-stu-id="68004-140">You can see the events of the alert, which other triggered alerts caused the current alert, and all the affected entities and activities involved in the attack, including files, users, and mailboxes.</span></span>

<span data-ttu-id="68004-141">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-141">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-alert-example.png" alt-text="Beispiel für eine Seite mit Warnungsdetails innerhalb eines Vorfalls":::

<span data-ttu-id="68004-143">Diese Vorfallwarnungsseite besteht aus den folgenden Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="68004-143">This incident alert page is composed of these sections:</span></span>

- <span data-ttu-id="68004-144">Warnungsartikel, der eine Zusammenfassung der Ereignisse enthält</span><span class="sxs-lookup"><span data-stu-id="68004-144">Alert story, which includes a summary of what happened</span></span>
- <span data-ttu-id="68004-145">Verwandte Ereignisse und Warnungen</span><span class="sxs-lookup"><span data-stu-id="68004-145">Related events and alerts</span></span>
- <span data-ttu-id="68004-146">Zusammenfassungsdetails</span><span class="sxs-lookup"><span data-stu-id="68004-146">Summary details</span></span>

<span data-ttu-id="68004-147">Erfahren Sie, wie Sie die Warnungswarteschlange und die Warnungsseiten verwenden, um Warnungen zu [untersuchen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="68004-147">Learn how to use the alert queue and alert pages in [investigate alerts](investigate-alerts.md).</span></span>

## <a name="devices"></a><span data-ttu-id="68004-148">Geräte</span><span class="sxs-lookup"><span data-stu-id="68004-148">Devices</span></span>

<span data-ttu-id="68004-149">Auf der Registerkarte **"Geräte"** werden alle Geräte aufgelistet, die sich auf den Vorfall beziehen.</span><span class="sxs-lookup"><span data-stu-id="68004-149">The **Devices** tab lists all the devices related to the incident.</span></span> <span data-ttu-id="68004-150">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-150">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Beispiel für eine Seite &quot;Geräte&quot; für einen Vorfall":::

<span data-ttu-id="68004-152">Sie können das Häkchen für ein Gerät aktivieren, um Details zu Gerät, Verzeichnisdaten, aktiven Warnungen und angemeldeten Benutzern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-152">You can select the check mark for a device to see details of the device, directory data, active alerts, and logged on users.</span></span> <span data-ttu-id="68004-153">Wählen Sie den Namen des Geräts aus, um Gerätedetails im Microsoft Defender für Endpunkte-Gerätebestand anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-153">Select the name of the device to see device details in the Microsoft Defender for Endpoints device inventory.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Beispiel für eine Geräteseite für Microsoft Defender für Endpunkte":::

<span data-ttu-id="68004-155">Auf der Geräteseite können Sie zusätzliche Informationen über das Gerät sammeln, z. B. alle Warnungen, eine Zeitachse und Sicherheitsempfehlungen.</span><span class="sxs-lookup"><span data-stu-id="68004-155">From the device page, you can gather additional information about the device, such as all of its alerts, a timeline, and security recommendations.</span></span> <span data-ttu-id="68004-156">Beispielsweise können Sie auf der Registerkarte **"Zeitachse"** einen Bildlauf durch die Computerzeitachse durchführen und alle auf dem Computer beobachteten Ereignisse und Verhaltensweisen in chronologischer Reihenfolge anzeigen, durchsetzt mit den ausgelösten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="68004-156">For example, from the **Timeline** tab, you can scroll through the machine timeline and view all events and behaviors observed on the machine in chronological order, interspersed with the alerts raised.</span></span>

> [!TIP]
> <span data-ttu-id="68004-157">Sie können Scans bei Bedarf auf einer Geräteseite durchführen.</span><span class="sxs-lookup"><span data-stu-id="68004-157">You can do on-demand scans on a device page.</span></span> <span data-ttu-id="68004-158">Wählen Sie im Microsoft 365 Security Center **Endpunkte > Gerätebestand** aus.</span><span class="sxs-lookup"><span data-stu-id="68004-158">In the Microsoft 365 security center, choose **Endpoints > Device inventory**.</span></span> <span data-ttu-id="68004-159">Wählen Sie ein Gerät mit Warnungen aus, und führen Sie dann einen Antivirenscan aus.</span><span class="sxs-lookup"><span data-stu-id="68004-159">Select a device that has alerts, and then run an antivirus scan.</span></span> <span data-ttu-id="68004-160">Aktionen, z. B. Antivirenscans, werden nachverfolgt und auf der **Gerätebestandsseite** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68004-160">Actions, such as antivirus scans, are tracked and are visible on the **Device inventory** page.</span></span> <span data-ttu-id="68004-161">Weitere Informationen finden Sie unter [Ausführen Microsoft Defender Antivirus Überprüfung auf Geräten.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)</span><span class="sxs-lookup"><span data-stu-id="68004-161">To learn more, see [Run Microsoft Defender Antivirus scan on devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices).</span></span>

## <a name="users"></a><span data-ttu-id="68004-162">Benutzer</span><span class="sxs-lookup"><span data-stu-id="68004-162">Users</span></span>

<span data-ttu-id="68004-163">Auf der Registerkarte **"Benutzer"** sind alle Benutzer aufgeführt, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="68004-163">The **Users** tab lists all the users that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="68004-164">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-164">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Beispiel für eine Seite &quot;Benutzer&quot; für einen Vorfall":::

<span data-ttu-id="68004-166">Sie können das Häkchen für einen Benutzer aktivieren, um Details zu Bedrohung, Gefährdung und Kontaktinformationen des Benutzerkontos anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-166">You can select the check mark for a user to see details of the user account threat, exposure, and contact information.</span></span> <span data-ttu-id="68004-167">Wählen Sie den Benutzernamen aus, um weitere Benutzerkontodetails anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-167">Select the user name to see additional user account details.</span></span>

<span data-ttu-id="68004-168">Erfahren Sie, wie Sie zusätzliche Benutzerinformationen anzeigen und die Benutzer eines Vorfalls bei der Untersuchung von [Benutzern](investigate-users.md)verwalten.</span><span class="sxs-lookup"><span data-stu-id="68004-168">Learn how to view additional user information and manage the users of an incident in [investigate users](investigate-users.md).</span></span>


## <a name="mailboxes"></a><span data-ttu-id="68004-169">Postfächer</span><span class="sxs-lookup"><span data-stu-id="68004-169">Mailboxes</span></span>

<span data-ttu-id="68004-170">Auf der Registerkarte **"Postfächer"** werden alle Postfächer aufgelistet, die als Teil des Vorfalls oder im Zusammenhang mit dem Vorfall identifiziert wurden.</span><span class="sxs-lookup"><span data-stu-id="68004-170">The **Mailboxes** tab lists all the mailboxes that have been identified to be part of or related to the incident.</span></span> <span data-ttu-id="68004-171">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-171">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Beispiel für eine Seite &quot;Postfächer&quot; für einen Vorfall":::

<span data-ttu-id="68004-173">Sie können das Häkchen für ein Postfach aktivieren, um eine Liste aktiver Warnungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-173">You can select the check mark for a mailbox to see a list of active alerts.</span></span> <span data-ttu-id="68004-174">Wählen Sie den Postfachnamen aus, um zusätzliche Postfachdetails auf der Explorer-Seite für Microsoft Defender für Office 365 anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="68004-174">Select the mailbox name to see additional mailbox details on the Explorer page for Microsoft Defender for Office 365.</span></span>

## <a name="investigations"></a><span data-ttu-id="68004-175">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="68004-175">Investigations</span></span>

<span data-ttu-id="68004-176">Die Registerkarte **"Untersuchungen"** listet alle [automatisierten Untersuchungen auf,](m365d-autoir.md) die durch Warnungen in diesem Vorfall ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="68004-176">The **Investigations** tab lists all the [automated investigations](m365d-autoir.md) triggered by alerts in this incident.</span></span> <span data-ttu-id="68004-177">Die Untersuchungen führen Korrekturmaßnahmen aus oder warten auf die Genehmigung von Aktionen durch den Analysten, je nachdem, wie Sie Ihre automatisierten Untersuchungen so konfiguriert haben, dass sie in Microsoft Defender für Endpunkt und Defender für Office 365 ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="68004-177">The investigations will perform remediation actions or wait for analyst approval of actions, depending on how you configured your automated investigations to run in Microsoft Defender for Endpoint and Defender for Office 365.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Beispiel für eine Seite &quot;Untersuchungen&quot; für einen Vorfall":::

<span data-ttu-id="68004-179">Wählen Sie eine Untersuchung aus, um zur Detailseite zu navigieren, um vollständige Informationen zum Untersuchungs- und Wartungsstatus zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68004-179">Select an investigation to navigate to its details page for full information on the investigation and remediation status.</span></span> <span data-ttu-id="68004-180">Wenn im Rahmen der Untersuchung Aktionen zur Genehmigung ausstehen, werden sie auf der Registerkarte **"Verlauf ausstehender Aktionen"** angezeigt. Ergreifen sie Maßnahmen im Rahmen der Vorfallbehebung.</span><span class="sxs-lookup"><span data-stu-id="68004-180">If there are any actions pending for approval as part of the investigation, they will appear in the **Pending actions history** tab. Take action as part of incident remediation.</span></span>

<span data-ttu-id="68004-181">Es gibt auch eine Registerkarte **"Untersuchungsdiagramm",** die Zeigt:</span><span class="sxs-lookup"><span data-stu-id="68004-181">There is also an **Investigation graph** tab that shows:</span></span>

- <span data-ttu-id="68004-182">Die Verbindung von Warnungen zu den betroffenen Ressourcen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="68004-182">The connection of alerts to the impacted assets in your organization.</span></span>
- <span data-ttu-id="68004-183">Welche Entitäten mit welchen Warnungen zusammenhängen und wie sie Teil der Geschichte des Angriffs sind.</span><span class="sxs-lookup"><span data-stu-id="68004-183">Which entities are related to which alerts and how they are part of the story of the attack.</span></span>
- <span data-ttu-id="68004-184">Die Warnungen für den Vorfall.</span><span class="sxs-lookup"><span data-stu-id="68004-184">The alerts for the incident.</span></span>

<span data-ttu-id="68004-185">Das Untersuchungsdiagramm hilft Ihnen, den gesamten Umfang des Angriffs schnell zu verstehen, indem die verschiedenen verdächtigen Entitäten, die Teil des Angriffs sind, mit ihren verwandten Ressourcen wie Benutzern, Geräten und Postfächern verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="68004-185">The investigation graph helps you quickly understand the full scope of the attack by connecting the different suspicious entities that are part of the attack with their related assets such as users, devices, and mailboxes.</span></span> 

<span data-ttu-id="68004-186">Weitere Informationen finden Sie [unter "Automatisierte Untersuchung und Reaktion" in Microsoft 365 Defender.](m365d-autoir.md)</span><span class="sxs-lookup"><span data-stu-id="68004-186">For more information, see [Automated investigation and response in Microsoft 365 Defender](m365d-autoir.md).</span></span>

## <a name="evidence-and-response"></a><span data-ttu-id="68004-187">Nachweise und Antworten</span><span class="sxs-lookup"><span data-stu-id="68004-187">Evidence and Response</span></span>

<span data-ttu-id="68004-188">Auf der Registerkarte **"Nachweise und Reaktion"** werden alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen des Vorfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68004-188">The **Evidence and Response** tab shows all the supported events and suspicious entities in the alerts in the incident.</span></span> <span data-ttu-id="68004-189">Im Folgenden sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="68004-189">Here's an example.</span></span>

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Beispiel für eine Seite &quot;Nachweis und Reaktion&quot; für einen Vorfall":::

<span data-ttu-id="68004-191">Microsoft 365 Defender untersucht automatisch alle von den Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Informationen zu wichtigen E-Mails, Dateien, Prozessen, Diensten, IP-Adressen und mehr bereit.</span><span class="sxs-lookup"><span data-stu-id="68004-191">Microsoft 365 Defender automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with information about the important emails, files, processes, services, IP Addresses, and more.</span></span> <span data-ttu-id="68004-192">Auf diese Weise können Sie potenzielle Bedrohungen im Vorfall schnell erkennen und blockieren.</span><span class="sxs-lookup"><span data-stu-id="68004-192">This helps you quickly detect and block potential threats in the incident.</span></span>

<span data-ttu-id="68004-193">Jede der analysierten Entitäten ist mit einem Bewertungsstatus (bösartig, verdächtig, sauber) und einem Korrekturstatus gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="68004-193">Each of the analyzed entities is marked with a verdict (Malicious, Suspicious, Clean) and a remediation status.</span></span> <span data-ttu-id="68004-194">Dies hilft Ihnen, den Wartungsstatus des gesamten Vorfalls zu verstehen und zu verstehen, welche nächsten Schritte ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="68004-194">This helps you understand the remediation status of the entire incident and what next steps can be taken.</span></span>

## <a name="next-steps"></a><span data-ttu-id="68004-195">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="68004-195">Next steps</span></span>

<span data-ttu-id="68004-196">Bei Bedarf:</span><span class="sxs-lookup"><span data-stu-id="68004-196">As needed:</span></span>

- [<span data-ttu-id="68004-197">Untersuchen der Warnungen eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="68004-197">Investigate the alerts of an incident</span></span>](investigate-alerts.md)
- [<span data-ttu-id="68004-198">Untersuchen der Benutzer eines Vorfalls</span><span class="sxs-lookup"><span data-stu-id="68004-198">Investigate the users of an incident</span></span>](investigate-users.md)

## <a name="see-also"></a><span data-ttu-id="68004-199">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68004-199">See also</span></span>

- [<span data-ttu-id="68004-200">Übersicht über Vorfälle</span><span class="sxs-lookup"><span data-stu-id="68004-200">Incidents overview</span></span>](incidents-overview.md)
- [<span data-ttu-id="68004-201">Priorisieren von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="68004-201">Prioritize incidents</span></span>](incident-queue.md)
- [<span data-ttu-id="68004-202">Verwalten von Vorfällen</span><span class="sxs-lookup"><span data-stu-id="68004-202">Manage incidents</span></span>](manage-incidents.md)


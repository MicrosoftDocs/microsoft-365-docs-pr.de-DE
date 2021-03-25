---
title: Microsoft Defender Security Center Security Operations Dashboard
description: Verwenden Sie das Dashboard, um gefährdete Geräte zu identifizieren, den Status des Diensts zu verfolgen und Statistiken und Informationen zu Geräten und Warnungen anzuzeigen.
keywords: Dashboard, Warnungen, neu, in Bearbeitung, aufgelöst, Risiko, Gefährdete Geräte, Infektionen, Berichterstellung, Statistiken, Diagramme, Diagramme, Gesundheit, aktive Schadsoftwareerkennungen, Bedrohungskategorie, Kategorien, Kennwortdiebstahl, Ransomware, Exploit, Bedrohung, niedriger Schweregrad, aktive Schadsoftware
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bfa23138b1bab4abcdfa0b4b9d689a4a4cfc7fc1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064912"
---
# <a name="microsoft-defender-security-center-security-operations-dashboard"></a><span data-ttu-id="1575e-104">Microsoft Defender Security Center Security Operations Dashboard</span><span class="sxs-lookup"><span data-stu-id="1575e-104">Microsoft Defender Security Center Security operations dashboard</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="1575e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="1575e-105">**Applies to:**</span></span>
- [<span data-ttu-id="1575e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="1575e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="1575e-107">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1575e-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1575e-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1575e-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-abovefoldlink) 

<span data-ttu-id="1575e-109">Im **Dashboard für Sicherheitsvorgänge** werden die Erkennungs- und Reaktionsfunktionen für Endpunkte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1575e-109">The **Security operations dashboard** is where the endpoint detection and response capabilities are surfaced.</span></span> <span data-ttu-id="1575e-110">Es bietet einen umfassenden Überblick darüber, wo Erkennungen angezeigt wurden, und hervorhebt, wo Reaktionsaktionen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="1575e-110">It provides a high level overview of where detections were seen and highlights where response actions are needed.</span></span> 

<span data-ttu-id="1575e-111">Das Dashboard zeigt eine Momentaufnahme von:</span><span class="sxs-lookup"><span data-stu-id="1575e-111">The dashboard displays a snapshot of:</span></span>

- <span data-ttu-id="1575e-112">Aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="1575e-112">Active alerts</span></span>
- <span data-ttu-id="1575e-113">Gefährdete Geräte</span><span class="sxs-lookup"><span data-stu-id="1575e-113">Devices at risk</span></span>
- <span data-ttu-id="1575e-114">Sensorinte health</span><span class="sxs-lookup"><span data-stu-id="1575e-114">Sensor health</span></span>
- <span data-ttu-id="1575e-115">Dienststatus</span><span class="sxs-lookup"><span data-stu-id="1575e-115">Service health</span></span>
- <span data-ttu-id="1575e-116">Tägliche Geräteberichte</span><span class="sxs-lookup"><span data-stu-id="1575e-116">Daily devices reporting</span></span>
- <span data-ttu-id="1575e-117">Aktive automatisierte Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1575e-117">Active automated investigations</span></span>
- <span data-ttu-id="1575e-118">Statistiken zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1575e-118">Automated investigations statistics</span></span>
- <span data-ttu-id="1575e-119">Gefährdete Benutzer</span><span class="sxs-lookup"><span data-stu-id="1575e-119">Users at risk</span></span>
- <span data-ttu-id="1575e-120">Verdächtige Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="1575e-120">Suspicious activities</span></span>


![Abbildung des Dashboards für Sicherheitsvorgänge](images/atp-sec-ops-dashboard.png)

<span data-ttu-id="1575e-122">Sie können Warnungen und Geräte erkunden und untersuchen, um schnell zu ermitteln, ob, wo und wann verdächtige Aktivitäten in Ihrem Netzwerk aufgetreten sind, um den Kontext zu verstehen, in dem sie aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="1575e-122">You can explore and investigate alerts and devices to quickly determine if, where, and when suspicious activities occurred in your network to help you understand the context they appeared in.</span></span>

<span data-ttu-id="1575e-123">Im **Dashboard für Sicherheitsvorgänge** werden aggregierte Ereignisse angezeigt, um die Identifizierung wichtiger Ereignisse oder Verhaltensweisen auf einem Gerät zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="1575e-123">From the **Security operations dashboard** you will see aggregated events to facilitate the identification of significant events or behaviors on a device.</span></span> <span data-ttu-id="1575e-124">Sie können auch detaillierte Informationen zu detaillierten Ereignissen und Indikatoren auf niedriger Ebene anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1575e-124">You can also drill down into granular events and low-level indicators.</span></span>

<span data-ttu-id="1575e-125">Es verfügt auch über klickbare Kacheln, die visuelle Hinweise auf den allgemeinen Integritätsstatus Ihrer Organisation geben.</span><span class="sxs-lookup"><span data-stu-id="1575e-125">It also has clickable tiles that give visual cues on the overall health state of your organization.</span></span> <span data-ttu-id="1575e-126">Jede Kachel öffnet eine detaillierte Ansicht der entsprechenden Übersicht.</span><span class="sxs-lookup"><span data-stu-id="1575e-126">Each tile opens a detailed view of the corresponding overview.</span></span>

## <a name="active-alerts"></a><span data-ttu-id="1575e-127">Aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="1575e-127">Active alerts</span></span>
<span data-ttu-id="1575e-128">Sie können die Gesamtzahl der aktiven Warnungen aus den letzten 30 Tagen in Ihrem Netzwerk über die Kachel anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1575e-128">You can view the overall number of active alerts from the last 30 days in your network from the tile.</span></span> <span data-ttu-id="1575e-129">Warnungen werden in **Neu und** In **Bearbeitung gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="1575e-129">Alerts are grouped into **New** and **In progress**.</span></span>

![Klicken Sie auf jeden Datenschnitt oder Schweregrad, um eine Liste der Warnungen aus den letzten 30 Tagen anzuzeigen.](images/active-alerts-tile.png)

<span data-ttu-id="1575e-131">Jede Gruppe wird in die entsprechenden Warnungsschweregrade unter kategorisiert.</span><span class="sxs-lookup"><span data-stu-id="1575e-131">Each group is further sub-categorized into their corresponding alert severity levels.</span></span> <span data-ttu-id="1575e-132">Klicken Sie auf die Anzahl der Warnungen in den einzelnen Warnungsringen, um eine sortierte Ansicht der Warteschlange dieser Kategorie anzuzeigen (**Neu** oder **In Bearbeitung**).</span><span class="sxs-lookup"><span data-stu-id="1575e-132">Click the number of alerts inside each alert ring to see a sorted view of that category's queue (**New** or **In progress**).</span></span>

<span data-ttu-id="1575e-133">Weitere Informationen finden Sie unter [Alerts overview](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-133">For more information see, [Alerts overview](alerts-queue.md).</span></span>

<span data-ttu-id="1575e-134">Jede Zeile enthält eine Kategorie für den Warnungsschweregrad und eine kurze Beschreibung der Warnung.</span><span class="sxs-lookup"><span data-stu-id="1575e-134">Each row includes an alert severity category and a short description of the alert.</span></span> <span data-ttu-id="1575e-135">Sie können auf eine Warnung klicken, um die detaillierte Ansicht zu sehen.</span><span class="sxs-lookup"><span data-stu-id="1575e-135">You can click an alert to see its detailed view.</span></span> <span data-ttu-id="1575e-136">Weitere Informationen finden Sie unter  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and Alerts [overview](alerts-queue.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-136">For more information see,  [Investigate Microsoft Defender for Endpoint alerts](investigate-alerts.md) and [Alerts overview](alerts-queue.md).</span></span>


## <a name="devices-at-risk"></a><span data-ttu-id="1575e-137">Gefährdete Geräte</span><span class="sxs-lookup"><span data-stu-id="1575e-137">Devices at risk</span></span>
<span data-ttu-id="1575e-138">Diese Kachel zeigt eine Liste der Geräte mit der höchsten Anzahl aktiver Warnungen.</span><span class="sxs-lookup"><span data-stu-id="1575e-138">This tile shows you a list of devices with the highest number of active alerts.</span></span> <span data-ttu-id="1575e-139">Die Gesamtanzahl der Warnungen für jedes Gerät wird in einem Kreis neben dem Gerätenamen angezeigt und dann weiter nach Schweregraden am ende der Kachel kategorisiert (zeigen Sie auf jeden Schweregradbalken, um dessen Bezeichnung anzuzeigen).</span><span class="sxs-lookup"><span data-stu-id="1575e-139">The total number of alerts for each device is shown in a circle next to the device name, and then further categorized by severity levels at the far end of the tile (hover over each severity bar to see its label).</span></span>

![Die Kachel Geräte mit Risiken zeigt eine Liste der Geräte mit der höchsten Anzahl von Warnungen und eine Aufschlüsselung des Schweregrads der Warnungen an.](images/devices-at-risk-tile.png)

<span data-ttu-id="1575e-141">Klicken Sie auf den Namen des Geräts, um Details zu diesem Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1575e-141">Click the name of the device to see details about that device.</span></span> <span data-ttu-id="1575e-142">Weitere Informationen finden Sie unter [Untersuchen von Geräten in der Liste Microsoft Defender for Endpoint Devices](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-142">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

<span data-ttu-id="1575e-143">Sie können auch oben auf **der** Kachel auf Geräteliste klicken, um direkt zur Geräteliste **zu** wechseln, sortiert nach der Anzahl der aktiven Warnungen.</span><span class="sxs-lookup"><span data-stu-id="1575e-143">You can also click **Devices list** at the top of the tile to go directly to the **Devices list**, sorted by the number of active alerts.</span></span> <span data-ttu-id="1575e-144">Weitere Informationen finden Sie unter [Untersuchen von Geräten in der Liste Microsoft Defender for Endpoint Devices](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-144">For more information see, [Investigate devices in the Microsoft Defender for Endpoint Devices list](investigate-machines.md).</span></span>

## <a name="devices-with-sensor-issues"></a><span data-ttu-id="1575e-145">Geräte mit Sensorproblemen</span><span class="sxs-lookup"><span data-stu-id="1575e-145">Devices with sensor issues</span></span>
<span data-ttu-id="1575e-146">Die **Kachel Geräte mit Sensorproblemen** enthält Informationen zur Fähigkeit des einzelnen Geräts, Sensordaten für den Microsoft Defender for Endpoint-Dienst zur Verfügung zu stellen.</span><span class="sxs-lookup"><span data-stu-id="1575e-146">The **Devices with sensor issues** tile provides information on the individual device’s ability to provide sensor data to the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="1575e-147">Es berichtet, wie viele Geräte Aufmerksamkeit erfordern und hilft Ihnen, problematische Geräte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1575e-147">It reports how many devices require attention and helps you identify problematic devices.</span></span>

![Geräte mit Einer Kachel mit Sensorproblemen](images/atp-tile-sensor-health.png)

<span data-ttu-id="1575e-149">Es gibt zwei Statusindikatoren, die Informationen zur Anzahl der Geräte bereitstellen, die dem Dienst nicht ordnungsgemäß melden:</span><span class="sxs-lookup"><span data-stu-id="1575e-149">There are two status indicators that provide information on the number of devices that are not reporting properly to the service:</span></span>
- <span data-ttu-id="1575e-150">**Falsch konfiguriert –** Diese Geräte melden möglicherweise teilweise Sensordaten an den Microsoft Defender for Endpoint-Dienst und können Konfigurationsfehler haben, die korrigiert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="1575e-150">**Misconfigured** – These devices might partially be reporting sensor data to the Microsoft Defender for Endpoint service and might have configuration errors that need to be corrected.</span></span>
- <span data-ttu-id="1575e-151">**Inaktiv** – Geräte, die die Berichterstellung an den Microsoft Defender for Endpoint-Dienst im letzten Monat für mehr als sieben Tage beendet haben.</span><span class="sxs-lookup"><span data-stu-id="1575e-151">**Inactive** - Devices that have stopped reporting to the Microsoft Defender for Endpoint service for more than seven days in the past month.</span></span>

<span data-ttu-id="1575e-152">Wenn Sie auf eine der Gruppen klicken, werden Sie zu der Geräteliste geleitet, die nach Ihrer Wahl gefiltert wird.</span><span class="sxs-lookup"><span data-stu-id="1575e-152">When you click any of the groups, you’ll be directed to devices list, filtered according to your choice.</span></span> <span data-ttu-id="1575e-153">Weitere Informationen finden Sie unter [Überprüfen des Sensorstatus und](check-sensor-status.md) Untersuchen von [Geräten](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-153">For more information, see [Check sensor state](check-sensor-status.md) and [Investigate devices](investigate-machines.md).</span></span>

## <a name="service-health"></a><span data-ttu-id="1575e-154">Dienststatus</span><span class="sxs-lookup"><span data-stu-id="1575e-154">Service health</span></span>
<span data-ttu-id="1575e-155">Die **Kachel Dienstintehzustand** informiert Sie, ob der Dienst aktiv ist oder probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="1575e-155">The **Service health** tile informs you if the service is active or if there are issues.</span></span>

![Die Kachel Dienstintehzustand zeigt einen allgemeinen Indikator des Diensts an.](images/status-tile.png)

<span data-ttu-id="1575e-157">Weitere Informationen zum Dienstzustand finden Sie unter [Überprüfen der Integrität des Microsoft Defender for Endpoint-Diensts](service-status.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-157">For more information on the service health, see [Check the Microsoft Defender for Endpoint service health](service-status.md).</span></span>


## <a name="daily-devices-reporting"></a><span data-ttu-id="1575e-158">Tägliche Geräteberichte</span><span class="sxs-lookup"><span data-stu-id="1575e-158">Daily devices reporting</span></span>
<span data-ttu-id="1575e-159">Die **Kachel Tägliche Gerätebericht** zeigt ein Balkendiagramm, das die Anzahl der Täglichen Berichte in den letzten 30 Tagen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1575e-159">The **Daily devices reporting** tile shows a bar graph that represents the number of devices reporting daily in the last 30 days.</span></span> <span data-ttu-id="1575e-160">Zeigen Sie auf einzelne Balken im Diagramm, um die genaue Anzahl der Geräte anzuzeigen, die jeden Tag berichten.</span><span class="sxs-lookup"><span data-stu-id="1575e-160">Hover over individual bars on the graph to see the exact number of devices reporting in each day.</span></span>

![Abbildung der Kachel für tägliche Geräteberichte](images/atp-daily-devices-reporting.png)


## <a name="active-automated-investigations"></a><span data-ttu-id="1575e-162">Aktive automatisierte Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1575e-162">Active automated investigations</span></span>
<span data-ttu-id="1575e-163">Sie können die Gesamtzahl der automatisierten Untersuchungen aus den letzten 30 Tagen in Ihrem Netzwerk auf der **Kachel Aktive automatisierte Untersuchungen** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1575e-163">You can view the overall number of automated investigations from the last 30 days in your network from the **Active automated investigations** tile.</span></span> <span data-ttu-id="1575e-164">Untersuchungen werden in **ausstehende** Aktion, **Warten auf Gerät** und Ausführen **gruppieren.**</span><span class="sxs-lookup"><span data-stu-id="1575e-164">Investigations are grouped into **Pending action**, **Waiting for device**, and **Running**.</span></span>

![Inmage von aktiven automatisierten Untersuchungen](images/atp-active-investigations-tile.png)


## <a name="automated-investigations-statistics"></a><span data-ttu-id="1575e-166">Statistiken zu automatisierten Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="1575e-166">Automated investigations statistics</span></span>
<span data-ttu-id="1575e-167">Diese Kachel zeigt Statistiken zu automatisierten Untersuchungen in den letzten sieben Tagen.</span><span class="sxs-lookup"><span data-stu-id="1575e-167">This tile shows statistics related to automated investigations in the last seven days.</span></span> <span data-ttu-id="1575e-168">Sie zeigt die Anzahl der abgeschlossenen Untersuchungen, die Anzahl der erfolgreich behobenen Untersuchungen, die durchschnittliche Ausstehendzeit für die Untersuchung, die durchschnittliche Zeit für die Behebung einer Warnung, die Anzahl der untersuchten Warnungen und die Anzahl der Stunden automatisierung, die bei einer typischen manuellen Untersuchung gespeichert wurden.</span><span class="sxs-lookup"><span data-stu-id="1575e-168">It shows the number of investigations completed, the number of successfully remediated investigations, the average pending time it takes for an investigation to be initiated, the average time it takes to remediate an alert, the number of alerts investigated, and the number of hours of automation saved from a typical manual investigation.</span></span> 

![Abbildung der Statistiken zu automatisierten Untersuchungen](images/atp-automated-investigations-statistics.png)

<span data-ttu-id="1575e-170">Sie können auf **Automatisierte** **Untersuchungen,** Nachgefilterte Untersuchungen und  **untersuchte Warnungen** klicken, um zur Seite Untersuchungen zu navigieren, gefiltert nach der entsprechenden Kategorie.</span><span class="sxs-lookup"><span data-stu-id="1575e-170">You can click on **Automated investigations**, **Remediated investigations**, and **Alerts investigated** to navigate to the **Investigations** page, filtered by the appropriate category.</span></span> <span data-ttu-id="1575e-171">Auf diese Weise können Sie eine detaillierte Aufschlüsselung der Untersuchungen im Kontext sehen.</span><span class="sxs-lookup"><span data-stu-id="1575e-171">This lets you see a detailed breakdown of investigations in context.</span></span>

## <a name="users-at-risk"></a><span data-ttu-id="1575e-172">Gefährdete Benutzer</span><span class="sxs-lookup"><span data-stu-id="1575e-172">Users at risk</span></span>
<span data-ttu-id="1575e-173">Die Kachel zeigt eine Liste der Benutzerkonten mit den aktivsten Warnungen und der Anzahl der Warnungen, die bei hohen, mittleren oder niedrigen Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1575e-173">The tile shows you a list of user accounts with the most active alerts and the number of alerts seen on high, medium, or low alerts.</span></span> 

![Die Kachel "Risikokonten" zeigt eine Liste der Benutzerkonten mit der höchsten Anzahl von Warnungen und eine Aufschlüsselung des Schweregrads der Warnungen an.](images/atp-users-at-risk.png)

<span data-ttu-id="1575e-175">Klicken Sie auf das Benutzerkonto, um Details zum Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1575e-175">Click the user account to see details about the user account.</span></span> <span data-ttu-id="1575e-176">Weitere Informationen finden Sie [unter Untersuchen eines Benutzerkontos](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="1575e-176">For more information see [Investigate a user account](investigate-user.md).</span></span>

><span data-ttu-id="1575e-177">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="1575e-177">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1575e-178">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="1575e-178">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-secopsdashboard-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="1575e-179">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="1575e-179">Related topics</span></span>
- [<span data-ttu-id="1575e-180">Verstehen des Microsoft Defender for Endpoint-Portals</span><span class="sxs-lookup"><span data-stu-id="1575e-180">Understand the Microsoft Defender for Endpoint portal</span></span>](use.md)
- [<span data-ttu-id="1575e-181">Portalübersicht</span><span class="sxs-lookup"><span data-stu-id="1575e-181">Portal overview</span></span>](portal-overview.md)
- [<span data-ttu-id="1575e-182">Anzeigen des Dashboards & Bedrohungsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="1575e-182">View the Threat & Vulnerability Management dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="1575e-183">Anzeigen des Dashboards für die Bedrohungsanalyse und Ergreifen empfohlener Gegenmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="1575e-183">View the Threat analytics dashboard and take recommended mitigation actions</span></span>](threat-analytics.md)

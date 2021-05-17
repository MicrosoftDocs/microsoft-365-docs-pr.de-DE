---
title: Untersuchen von Geräten in der Liste "Defender for Endpoint Devices"
description: Untersuchen Sie betroffene Geräte, indem Sie Warnungen, Netzwerkverbindungsinformationen, Gerätetags und Gruppen hinzufügen und den Dienstzustand überprüfen.
keywords: Geräte, Tags, Gruppen, Endpunkt, Warnungswarteschlange, Warnungen, Gerätename, Domäne, zuletzt gesehen, interne IP, aktive Warnungen, Bedrohungskategorie, Filter, Sortierung, Warnungen überprüfen, Netzwerk, Verbindung, Typ, Kennwortdiebstahl, Ransomware, Exploit, Bedrohung, niedriger Schweregrad, Dienstintegheit
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c1e572910ad311daba18a8b0f5eeb546ffe36956
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929109"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="b3691-104">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="b3691-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b3691-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="b3691-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3691-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b3691-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3691-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3691-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b3691-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="b3691-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b3691-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="b3691-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="b3691-110">Untersuchen Sie die Details einer Warnung, die auf einem bestimmten Gerät ausgelöst wird, um andere Verhaltensweisen oder Ereignisse zu identifizieren, die im Zusammenhang mit der Warnung oder dem potenziellen Umfang der Verletzung stehen können.</span><span class="sxs-lookup"><span data-stu-id="b3691-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="b3691-111">Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="b3691-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="b3691-112">So geht's: [Erfassen des Untersuchungspakets von Geräten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="b3691-112">Here's how: [Collect investigation package from devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="b3691-113">Sie können auf betroffene Geräte klicken, wenn sie im Portal angezeigt werden, um einen detaillierten Bericht über dieses Gerät zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b3691-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="b3691-114">Betroffene Geräte werden in den folgenden Bereichen identifiziert:</span><span class="sxs-lookup"><span data-stu-id="b3691-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="b3691-115">Geräteliste</span><span class="sxs-lookup"><span data-stu-id="b3691-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="b3691-116">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="b3691-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="b3691-117">Dashboard für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="b3691-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="b3691-118">Jede einzelne Warnung</span><span class="sxs-lookup"><span data-stu-id="b3691-118">Any individual alert</span></span>
- <span data-ttu-id="b3691-119">Jede einzelne Dateidetailseansicht</span><span class="sxs-lookup"><span data-stu-id="b3691-119">Any individual file details view</span></span>
- <span data-ttu-id="b3691-120">Ansicht mit allen IP-Adressen oder Domänendetails</span><span class="sxs-lookup"><span data-stu-id="b3691-120">Any IP address or domain details view</span></span>

<span data-ttu-id="b3691-121">Wenn Sie ein bestimmtes Gerät untersuchen, sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="b3691-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="b3691-122">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="b3691-122">Device details</span></span>
- <span data-ttu-id="b3691-123">Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="b3691-123">Response actions</span></span>
- <span data-ttu-id="b3691-124">Registerkarten (Übersicht, Warnungen, Zeitachse, Sicherheitsempfehlungen, Softwareinventar, ermittelte Sicherheitsrisiken, fehlende KBs)</span><span class="sxs-lookup"><span data-stu-id="b3691-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="b3691-125">Karten (aktive Warnungen, angemeldete Benutzer, Sicherheitsbewertung)</span><span class="sxs-lookup"><span data-stu-id="b3691-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Abbildung der Geräteansicht](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="b3691-127">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="b3691-127">Device details</span></span>

<span data-ttu-id="b3691-128">Der Abschnitt Gerätedetails enthält Informationen wie die Domäne, das Betriebssystem und den Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="b3691-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="b3691-129">Wenn auf dem Gerät ein Untersuchungspaket verfügbar ist, wird ein Link angezeigt, über den Sie das Paket herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="b3691-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="b3691-130">Reaktionsaktionen</span><span class="sxs-lookup"><span data-stu-id="b3691-130">Response actions</span></span>

<span data-ttu-id="b3691-131">Reaktionsaktionen werden am oberen Rand einer bestimmten Geräteseite ausgeführt und umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="b3691-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="b3691-132">Verwalten von Kategorien</span><span class="sxs-lookup"><span data-stu-id="b3691-132">Manage tags</span></span>
- <span data-ttu-id="b3691-133">Isolieren des Geräts</span><span class="sxs-lookup"><span data-stu-id="b3691-133">Isolate device</span></span>
- <span data-ttu-id="b3691-134">Einschränken der App-Ausführung</span><span class="sxs-lookup"><span data-stu-id="b3691-134">Restrict app execution</span></span>
- <span data-ttu-id="b3691-135">Antivirusscan ausführen</span><span class="sxs-lookup"><span data-stu-id="b3691-135">Run antivirus scan</span></span>
- <span data-ttu-id="b3691-136">Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="b3691-136">Collect investigation package</span></span>
- <span data-ttu-id="b3691-137">Initiieren der Liveantwortsitzung</span><span class="sxs-lookup"><span data-stu-id="b3691-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="b3691-138">Initiieren einer automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="b3691-138">Initiate automated investigation</span></span>
- <span data-ttu-id="b3691-139">Wenden Sie sich an einen Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="b3691-139">Consult a threat expert</span></span>
- <span data-ttu-id="b3691-140">Info-Center</span><span class="sxs-lookup"><span data-stu-id="b3691-140">Action center</span></span>

<span data-ttu-id="b3691-141">Sie können Reaktionsaktionen im Aktionscenter, auf einer bestimmten Geräteseite oder auf einer bestimmten Dateiseite ausführen.</span><span class="sxs-lookup"><span data-stu-id="b3691-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="b3691-142">Weitere Informationen zum Ergreifen von Aktionen auf einem Gerät finden Sie unter [Take response action on a device](respond-machine-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="b3691-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="b3691-143">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="b3691-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="b3691-144">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="b3691-144">Tabs</span></span>

<span data-ttu-id="b3691-145">Die Registerkarten bieten relevante Sicherheits- und Bedrohungsschutzinformationen im Zusammenhang mit dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="b3691-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="b3691-146">Auf jeder Registerkarte können Sie die angezeigten  Spalten anpassen, indem Sie Spalten in der Leiste oberhalb der Spaltenüberschriften anpassen auswählen.</span><span class="sxs-lookup"><span data-stu-id="b3691-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="b3691-147">Übersicht</span><span class="sxs-lookup"><span data-stu-id="b3691-147">Overview</span></span>
<span data-ttu-id="b3691-148">Auf **der** Registerkarte Übersicht werden die [Karten für](#cards) aktive Warnungen, angemeldete Benutzer und Sicherheitsbewertung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3691-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Abbildung der Registerkarte Übersicht auf der Geräteseite](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="b3691-150">Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3691-150">Alerts</span></span>

<span data-ttu-id="b3691-151">Die **Registerkarte Warnungen** enthält eine Liste der Warnungen, die dem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="b3691-152">Diese Liste ist eine gefilterte Version der Warnungswarteschlange [und](alerts-queue.md)zeigt eine kurze Beschreibung der Warnung, des Schweregrads (hoch, mittel, niedrig, informationsell), des Status in der Warteschlange (neu, in Bearbeitung, aufgelöst), der Klassifizierung (nicht festgelegt, falscher Alarm, wahrer Alarm), des Untersuchungsstatus, der Kategorie der Warnung, der Adressierung der Warnung und der letzten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="b3691-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="b3691-153">Sie können die Warnungen auch filtern.</span><span class="sxs-lookup"><span data-stu-id="b3691-153">You can also filter the alerts.</span></span>

![Abbildung von Warnungen im Zusammenhang mit dem Gerät](images/alerts-device.png)

<span data-ttu-id="b3691-155">Wenn das Kreissymbol links neben einer Warnung ausgewählt ist, wird ein Fly-Out angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3691-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="b3691-156">In diesem Bereich können Sie die Warnung verwalten und weitere Details wie die Vorfallnummer und zugehörige Geräte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="b3691-157">Mehrere Warnungen können gleichzeitig ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="b3691-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="b3691-158">Wählen Sie den Titel der Warnung aus, um eine vollständige Seitenansicht einer Warnung einschließlich eines Vorfalldiagramms und einer Prozessstruktur anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="b3691-159">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="b3691-159">Timeline</span></span>

<span data-ttu-id="b3691-160">Die **Registerkarte Zeitachse** bietet eine chronologische Ansicht der Ereignisse und zugeordneten Warnungen, die auf dem Gerät beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="b3691-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="b3691-161">Dadurch können Sie Ereignisse, Dateien und IP-Adressen in Bezug auf das Gerät korrelieren.</span><span class="sxs-lookup"><span data-stu-id="b3691-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="b3691-162">Die Zeitachse ermöglicht es Ihnen auch, einen selektiven Drilldown auf Ereignisse zu erstellen, die innerhalb eines bestimmten Zeitraums aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="b3691-163">Sie können die zeitliche Abfolge von Ereignissen anzeigen, die auf einem Gerät über einen ausgewählten Zeitraum aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="b3691-164">Um Ihre Ansicht weiter zu steuern, können Sie nach Ereignisgruppen filtern oder die Spalten anpassen.</span><span class="sxs-lookup"><span data-stu-id="b3691-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="b3691-165">Damit Firewallereignisse angezeigt werden, müssen Sie die Überwachungsrichtlinie aktivieren, siehe [Überwachung filterplattformverbindung](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span><span class="sxs-lookup"><span data-stu-id="b3691-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="b3691-166">Firewall deckt die folgenden Ereignisse ab</span><span class="sxs-lookup"><span data-stu-id="b3691-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="b3691-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) – Firewalldienst beendet</span><span class="sxs-lookup"><span data-stu-id="b3691-167">[5025](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="b3691-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) – Anwendung blockiert, eingehende Verbindungen im Netzwerk zu akzeptieren</span><span class="sxs-lookup"><span data-stu-id="b3691-168">[5031](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="b3691-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) – blockierte Verbindung</span><span class="sxs-lookup"><span data-stu-id="b3691-169">[5157](https://docs.microsoft.com/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Abbildung der Gerätezeitachse mit Ereignissen](images/timeline-device.png)

<span data-ttu-id="b3691-171">Zu den Funktionen gehören:</span><span class="sxs-lookup"><span data-stu-id="b3691-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="b3691-172">Suchen nach bestimmten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="b3691-172">Search for specific events</span></span>
  - <span data-ttu-id="b3691-173">Verwenden Sie die Suchleiste, um nach bestimmten Zeitachsenereignissen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b3691-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="b3691-174">Filtern von Ereignissen aus einem bestimmten Datum</span><span class="sxs-lookup"><span data-stu-id="b3691-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="b3691-175">Wählen Sie das Kalendersymbol in der oberen linken Ecke der Tabelle aus, um Ereignisse im vergangenen Tag, in der letzten Woche, in 30 Tagen oder im benutzerdefinierten Bereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="b3691-176">Standardmäßig ist die Gerätezeitachse so festgelegt, dass die Ereignisse aus den letzten 30 Tagen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3691-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="b3691-177">Verwenden Sie die Zeitachse, um zu einem bestimmten Zeitpunkt zu springen, indem Sie den Abschnitt hervorheben.</span><span class="sxs-lookup"><span data-stu-id="b3691-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="b3691-178">Die Pfeile auf der Zeitachse zeigen automatisierte Untersuchungen an</span><span class="sxs-lookup"><span data-stu-id="b3691-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="b3691-179">Exportieren detaillierter Gerätezeitachsenereignisse</span><span class="sxs-lookup"><span data-stu-id="b3691-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="b3691-180">Exportieren Sie die Gerätezeitachse für das aktuelle Datum oder einen angegebenen Datumsbereich bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="b3691-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="b3691-181">Weitere Informationen zu bestimmten Ereignissen finden Sie im **Abschnitt Zusätzliche** Informationen.</span><span class="sxs-lookup"><span data-stu-id="b3691-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="b3691-182">Diese Details variieren je nach Ereignistyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="b3691-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="b3691-183">Von Application Guard enthalten – das Webbrowserereignis wurde durch einen isolierten Container eingeschränkt</span><span class="sxs-lookup"><span data-stu-id="b3691-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="b3691-184">Erkannte aktive Bedrohung – Die Bedrohungserkennung wurde während der Ausführung der Bedrohung erkannt.</span><span class="sxs-lookup"><span data-stu-id="b3691-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="b3691-185">Behebung nicht erfolgreich – Ein Versuch zur Behebung der erkannten Bedrohung wurde aufgerufen, aber fehlgeschlagen</span><span class="sxs-lookup"><span data-stu-id="b3691-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="b3691-186">Behebung erfolgreich – die erkannte Bedrohung wurde beendet und bereinigt</span><span class="sxs-lookup"><span data-stu-id="b3691-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="b3691-187">Vom Benutzer umgangene Warnung – die Windows Defender SmartScreen-Warnung wurde von einem Benutzer verworfen und überschrieben.</span><span class="sxs-lookup"><span data-stu-id="b3691-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="b3691-188">Verdächtiges Skript erkannt – Es wurde ein potenziell schädliches Skript gefunden, das ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="b3691-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="b3691-189">Die Warnungskategorie – wenn das Ereignis zur Generierung einer Warnung geführt hat, wird die Warnungskategorie ("Laterale Bewegung" z. B. ) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="b3691-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="b3691-190">Ereignisdetails</span><span class="sxs-lookup"><span data-stu-id="b3691-190">Event details</span></span>
<span data-ttu-id="b3691-191">Wählen Sie ein Ereignis aus, um relevante Details zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="b3691-192">Ein Bereich wird angezeigt, um allgemeine Ereignisinformationen zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-192">A panel displays to show general event information.</span></span> <span data-ttu-id="b3691-193">Wenn zutreffend und Daten verfügbar sind, wird auch ein Diagramm mit verwandten Entitäten und deren Beziehungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3691-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="b3691-194">Um das Ereignis und die zugehörigen Ereignisse [](advanced-hunting-overview.md) weiter zu untersuchen, können Sie schnell eine erweiterte Suchabfrage ausführen, indem **Sie Hunt für verwandte Ereignisse auswählen.**</span><span class="sxs-lookup"><span data-stu-id="b3691-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="b3691-195">Die Abfrage gibt das ausgewählte Ereignis und die Liste der anderen Ereignisse zurück, die etwa zur gleichen Zeit auf demselben Endpunkt aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Abbildung des Ereignisdetailsepanels](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="b3691-197">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="b3691-197">Security recommendations</span></span>

<span data-ttu-id="b3691-198">**Sicherheitsempfehlungen** werden aus der Bedrohungsverwaltungsfunktion von Microsoft Defender [& Endpoint](tvm-dashboard-insights.md) generiert.</span><span class="sxs-lookup"><span data-stu-id="b3691-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="b3691-199">Wenn Sie eine Empfehlung auswählen, wird ein Panel angezeigt, in dem Sie relevante Details anzeigen können, z. B. die Beschreibung der Empfehlung und die potenziellen Risiken, die mit der nichten Umsetzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="b3691-200">Weitere [Informationen finden Sie unter Sicherheitsempfehlung.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="b3691-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Abbildung der Registerkarte "Sicherheitsempfehlungen"](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="b3691-202">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="b3691-202">Software inventory</span></span>

<span data-ttu-id="b3691-203">Auf **der Registerkarte Softwareinventar** können Sie Software auf dem Gerät sowie alle Schwächen oder Bedrohungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b3691-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="b3691-204">Wenn Sie den Namen der Software auswählen, gelangen Sie zur Seite mit den Softwaredetails, auf der Sie Sicherheitsempfehlungen, ermittelte Sicherheitsrisiken, installierte Geräte und Versionsverteilung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="b3691-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="b3691-205">Weitere [Informationen finden Sie unter Softwareinventar](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="b3691-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Abbildung der Registerkarte "Softwareinventar"](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="b3691-207">Gefundene Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="b3691-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="b3691-208">Auf **der Registerkarte Ermittelte Sicherheitsrisiken** werden der Name, der Schweregrad und die Bedrohungseinblicke entdeckter Sicherheitsrisiken auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3691-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="b3691-209">Wenn Sie bestimmte Sicherheitsrisiken auswählen, werden eine Beschreibung und Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b3691-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken"](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="b3691-211">Fehlende KBs</span><span class="sxs-lookup"><span data-stu-id="b3691-211">Missing KBs</span></span>
<span data-ttu-id="b3691-212">Auf der Registerkarte Fehlende **KBs** werden die fehlenden Sicherheitsupdates für das Gerät aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b3691-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Abbildung fehlender Kbs-Registerkarte](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="b3691-214">Karten</span><span class="sxs-lookup"><span data-stu-id="b3691-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="b3691-215">Aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3691-215">Active alerts</span></span>

<span data-ttu-id="b3691-216">Die **Azure Advanced Threat Protection-Karte** zeigt eine übersicht über Warnungen im Zusammenhang mit dem Gerät und deren Risikostufe an, wenn Sie das Microsoft Defender for Identity-Feature aktiviert haben und aktive Warnungen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b3691-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="b3691-217">Weitere Informationen finden Sie im Drilldown "Alerts".</span><span class="sxs-lookup"><span data-stu-id="b3691-217">More information is available in the "Alerts" drill down.</span></span>

![Abbildung der aktiven Benachrichtigungskarte](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="b3691-219">Sie müssen die Integration in Microsoft Defender for Identity und Defender for Endpoint aktivieren, um dieses Feature verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="b3691-219">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="b3691-220">In Defender for Endpoint können Sie dieses Feature in erweiterten Features aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b3691-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="b3691-221">Weitere Informationen zum Aktivieren erweiterter Features finden Sie unter [Turn on advanced features](advanced-features.md).</span><span class="sxs-lookup"><span data-stu-id="b3691-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="b3691-222">Angemeldete Benutzer</span><span class="sxs-lookup"><span data-stu-id="b3691-222">Logged on users</span></span>

<span data-ttu-id="b3691-223">Die **Karte Angemeldete** Benutzer zeigt an, wie viele Benutzer sich in den letzten 30 Tagen angemeldet haben, zusammen mit den meisten und am wenigsten häufigen Benutzern.</span><span class="sxs-lookup"><span data-stu-id="b3691-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="b3691-224">Wenn Sie den Link "Alle Benutzer anzeigen" auswählen, wird der Detailbereich geöffnet, in dem Informationen wie Benutzertyp, Anmeldetyp und der erste und letzte Benutzer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b3691-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="b3691-225">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten](investigate-user.md).</span><span class="sxs-lookup"><span data-stu-id="b3691-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Abbildung des Benutzerdetailsebereichs](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="b3691-227">Sicherheitsbewertungen</span><span class="sxs-lookup"><span data-stu-id="b3691-227">Security assessments</span></span>

<span data-ttu-id="b3691-228">Die **Karte "Sicherheitsbewertungen"** zeigt die allgemeine Belichtungsstufe, Sicherheitsempfehlungen, installierte Software und ermittelte Sicherheitsrisiken an.</span><span class="sxs-lookup"><span data-stu-id="b3691-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="b3691-229">Die Belichtungsstufe eines Geräts wird durch die kumulierten Auswirkungen der ausstehenden Sicherheitsempfehlungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b3691-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Abbildung der Sicherheitsbewertungskarte](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="b3691-231">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="b3691-231">Related topics</span></span>

- [<span data-ttu-id="b3691-232">Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange</span><span class="sxs-lookup"><span data-stu-id="b3691-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="b3691-233">Verwalten von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3691-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="b3691-234">Untersuchen von Microsoft Defender for Endpoint-Warnungen</span><span class="sxs-lookup"><span data-stu-id="b3691-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="b3691-235">Untersuchen einer Datei, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="b3691-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="b3691-236">Untersuchen einer einer Defender for Endpoint-Warnung zugeordneten IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="b3691-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="b3691-237">Untersuchen einer Domäne, die einer Defender for Endpoint-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="b3691-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="b3691-238">Untersuchen eines Benutzerkontos in Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b3691-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="b3691-239">Sicherheitsempfehlung</span><span class="sxs-lookup"><span data-stu-id="b3691-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="b3691-240">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="b3691-240">Software inventory</span></span>](tvm-software-inventory.md)

---
title: Untersuchen von Geräten in der Liste "Defender für Endpunktgeräte"
description: Untersuchen Sie betroffene Geräte durch Überprüfen von Warnungen, Netzwerkverbindungsinformationen, Hinzufügen von Gerätetags und -gruppen und Überprüfen des Dienststatus.
keywords: Geräte, Tags, Gruppen, Endpunkt, Warnungswarteschlange, Warnungen, Gerätename, Domäne, zuletzt gesehen, interne IP, aktive Warnungen, Bedrohungskategorie, filtern, sortieren, Warnungen überprüfen, Netzwerk, Verbindung, Typ, Kennwortdiebstahler, Ransomware, Exploit, Bedrohung, niedriger Schweregrad, Dienststatus
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
ms.openlocfilehash: c89de5fbf5d5b4d5d5e53074109bc8884a271eea
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394893"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="159eb-104">Untersuchen von Geräten in der Liste "Microsoft Defender für Endpunktgeräte"</span><span class="sxs-lookup"><span data-stu-id="159eb-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="159eb-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="159eb-105">**Applies to:**</span></span>
- [<span data-ttu-id="159eb-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="159eb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="159eb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="159eb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="159eb-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="159eb-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="159eb-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="159eb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="159eb-110">Untersuchen Sie die Details einer Warnung, die auf einem bestimmten Gerät ausgelöst wird, um andere Verhaltensweisen oder Ereignisse zu identifizieren, die mit der Warnung oder dem potenziellen Umfang der Verletzung zusammenhängen könnten.</span><span class="sxs-lookup"><span data-stu-id="159eb-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="159eb-111">Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="159eb-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="159eb-112">Hier sehen Sie, wie: [Erfassen Sie untersuchungspaket von Geräten](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="159eb-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="159eb-113">Sie können auf betroffene Geräte klicken, wenn sie im Portal angezeigt werden, um einen detaillierten Bericht zu diesem Gerät zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="159eb-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="159eb-114">Betroffene Geräte werden in den folgenden Bereichen identifiziert:</span><span class="sxs-lookup"><span data-stu-id="159eb-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="159eb-115">Geräteliste</span><span class="sxs-lookup"><span data-stu-id="159eb-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="159eb-116">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="159eb-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="159eb-117">Dashboard für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="159eb-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="159eb-118">Jede einzelne Warnung</span><span class="sxs-lookup"><span data-stu-id="159eb-118">Any individual alert</span></span>
- <span data-ttu-id="159eb-119">Jede einzelne Dateidetailseansicht</span><span class="sxs-lookup"><span data-stu-id="159eb-119">Any individual file details view</span></span>
- <span data-ttu-id="159eb-120">Alle IP-Adressen oder Domänendetails</span><span class="sxs-lookup"><span data-stu-id="159eb-120">Any IP address or domain details view</span></span>

<span data-ttu-id="159eb-121">Wenn Sie ein bestimmtes Gerät untersuchen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="159eb-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="159eb-122">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="159eb-122">Device details</span></span>
- <span data-ttu-id="159eb-123">Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="159eb-123">Response actions</span></span>
- <span data-ttu-id="159eb-124">Registerkarten (Übersicht, Warnungen, Zeitachse, Sicherheitsempfehlungen, Softwareinventarisierung, erkannte Sicherheitsrisiken, fehlende KBs)</span><span class="sxs-lookup"><span data-stu-id="159eb-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="159eb-125">Karten (aktive Warnungen, angemeldete Benutzer, Sicherheitsbewertung)</span><span class="sxs-lookup"><span data-stu-id="159eb-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Abbildung der Geräteansicht](images/specific-device.png)

> [!NOTE]
> <span data-ttu-id="159eb-127">Aufgrund von Produkteinschränkungen berücksichtigt das Geräteprofil nicht alle Cyberbeweise bei der Bestimmung des Zeitrahmens "Zuletzt gesehen" (siehe auch auf der Geräteseite).</span><span class="sxs-lookup"><span data-stu-id="159eb-127">Due to product constrains, the device profile does not consider all cyber evidence when determining the 'Last Seen' timeframe (as seen on the device page as well).</span></span>
> <span data-ttu-id="159eb-128">Beispielsweise kann der Wert "Zuletzt gesehen" auf der Geräteseite einen älteren Zeitrahmen anzeigen, obwohl aktuellere Warnungen oder Daten auf der Zeitachse des Computers verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-128">For example, the 'Last seen' value in the Device page may show an older time frame even though more recent alerts or data is available in the machine's timeline.</span></span>

## <a name="device-details"></a><span data-ttu-id="159eb-129">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="159eb-129">Device details</span></span>

<span data-ttu-id="159eb-130">Der Abschnitt "Gerätedetails" enthält Informationen wie Domäne, Betriebssystem und Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="159eb-130">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="159eb-131">Wenn ein Untersuchungspaket auf dem Gerät verfügbar ist, wird ein Link angezeigt, über den Sie das Paket herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="159eb-131">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="159eb-132">Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="159eb-132">Response actions</span></span>

<span data-ttu-id="159eb-133">Antwortaktionen werden oben auf einer bestimmten Geräteseite ausgeführt und umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="159eb-133">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="159eb-134">Verwalten von Kategorien</span><span class="sxs-lookup"><span data-stu-id="159eb-134">Manage tags</span></span>
- <span data-ttu-id="159eb-135">Gerät isolieren</span><span class="sxs-lookup"><span data-stu-id="159eb-135">Isolate device</span></span>
- <span data-ttu-id="159eb-136">App-Ausführung einschränken</span><span class="sxs-lookup"><span data-stu-id="159eb-136">Restrict app execution</span></span>
- <span data-ttu-id="159eb-137">Antivirusscan ausführen</span><span class="sxs-lookup"><span data-stu-id="159eb-137">Run antivirus scan</span></span>
- <span data-ttu-id="159eb-138">Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="159eb-138">Collect investigation package</span></span>
- <span data-ttu-id="159eb-139">Initiieren einer Liveantwortsitzung</span><span class="sxs-lookup"><span data-stu-id="159eb-139">Initiate Live Response Session</span></span>
- <span data-ttu-id="159eb-140">Initiieren einer automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="159eb-140">Initiate automated investigation</span></span>
- <span data-ttu-id="159eb-141">Wenden Sie sich an einen Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="159eb-141">Consult a threat expert</span></span>
- <span data-ttu-id="159eb-142">Info-Center</span><span class="sxs-lookup"><span data-stu-id="159eb-142">Action center</span></span>

<span data-ttu-id="159eb-143">Sie können Reaktionsaktionen im Info-Center, auf einer bestimmten Geräteseite oder auf einer bestimmten Dateiseite ausführen.</span><span class="sxs-lookup"><span data-stu-id="159eb-143">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="159eb-144">Weitere Informationen zum Ausführen von Maßnahmen auf einem Gerät finden Sie unter "Ergreifen von [Gegenmaßnahmen auf einem Gerät".](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-144">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="159eb-145">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-145">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="159eb-146">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="159eb-146">Tabs</span></span>

<span data-ttu-id="159eb-147">Die Registerkarten enthalten relevante Informationen zur Sicherheit und Bedrohungsverhütung im Zusammenhang mit dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="159eb-147">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="159eb-148">Auf jeder Registerkarte können Sie die angezeigten Spalten anpassen, indem Sie **Spalten** in der Leiste oberhalb der Spaltenüberschriften anpassen auswählen.</span><span class="sxs-lookup"><span data-stu-id="159eb-148">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="159eb-149">Übersicht</span><span class="sxs-lookup"><span data-stu-id="159eb-149">Overview</span></span>
<span data-ttu-id="159eb-150">Auf der Registerkarte **"Übersicht"** werden die [Karten](#cards) für aktive Warnungen, angemeldete Benutzer und Sicherheitsbewertungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-150">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Abbildung der Registerkarte "Übersicht" auf der Geräteseite](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="159eb-152">Warnungen</span><span class="sxs-lookup"><span data-stu-id="159eb-152">Alerts</span></span>

<span data-ttu-id="159eb-153">Die Registerkarte **"Warnungen"** enthält eine Liste der Warnungen, die dem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-153">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="159eb-154">Diese Liste ist eine gefilterte Version der [Warnungswarteschlange](alerts-queue.md)und zeigt eine kurze Beschreibung der Warnung, des Schweregrads (hoch, mittel, niedrig, informational), des Status in der Warteschlange (neu, in Bearbeitung, aufgelöst), der Klassifizierung (nicht festgelegt, falsch, true alert), des Untersuchungsstatus, der Kategorie der Warnung, der Adressierung der Warnung und der letzten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="159eb-154">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="159eb-155">Sie können die Warnungen auch filtern.</span><span class="sxs-lookup"><span data-stu-id="159eb-155">You can also filter the alerts.</span></span>

![Abbildung von Warnungen im Zusammenhang mit dem Gerät](images/alerts-device.png)

<span data-ttu-id="159eb-157">Wenn das Kreissymbol links neben einer Warnung ausgewählt ist, wird ein Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-157">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="159eb-158">In diesem Bereich können Sie die Warnung verwalten und weitere Details wie die Vorfallnummer und verwandte Geräte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="159eb-158">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="159eb-159">Mehrere Warnungen können gleichzeitig ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="159eb-159">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="159eb-160">Um eine vollständige Seitenansicht einer Warnung einschließlich Vorfalldiagramm und Prozessstruktur anzuzeigen, wählen Sie den Titel der Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="159eb-160">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="159eb-161">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="159eb-161">Timeline</span></span>

<span data-ttu-id="159eb-162">Die Registerkarte **"Zeitachse"** bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die auf dem Gerät beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="159eb-162">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="159eb-163">Dies kann Ihnen dabei helfen, ereignisse, Dateien und IP-Adressen in Bezug auf das Gerät zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="159eb-163">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="159eb-164">Auf der Zeitachse können Sie auch selektiv Einen Drilldown zu Ereignissen ausführen, die innerhalb eines bestimmten Zeitraums aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-164">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="159eb-165">Sie können die zeitliche Abfolge von Ereignissen anzeigen, die über einen ausgewählten Zeitraum auf einem Gerät aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-165">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="159eb-166">Um die Ansicht weiter zu steuern, können Sie nach Ereignisgruppen filtern oder die Spalten anpassen.</span><span class="sxs-lookup"><span data-stu-id="159eb-166">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="159eb-167">Zum Anzeigen von Firewallereignissen müssen Sie die Überwachungsrichtlinie aktivieren. Weitere Informationen finden Sie unter ["Audit Filtering Platform connection".](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="159eb-167">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="159eb-168">Firewall deckt die folgenden Ereignisse ab</span><span class="sxs-lookup"><span data-stu-id="159eb-168">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="159eb-169">[5025](/windows/security/threat-protection/auditing/event-5025) – Firewalldienst beendet</span><span class="sxs-lookup"><span data-stu-id="159eb-169">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="159eb-170">[5031](/windows/security/threat-protection/auditing/event-5031) – Anwendung, die am Akzeptieren eingehender Verbindungen im Netzwerk gehindert wird</span><span class="sxs-lookup"><span data-stu-id="159eb-170">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="159eb-171">[5157 –](/windows/security/threat-protection/auditing/event-5157) blockierte Verbindung</span><span class="sxs-lookup"><span data-stu-id="159eb-171">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Abbildung der Gerätezeitachse mit Ereignissen](images/timeline-device.png)

<span data-ttu-id="159eb-173">Einige der Funktionen umfassen:</span><span class="sxs-lookup"><span data-stu-id="159eb-173">Some of the functionality includes:</span></span>

- <span data-ttu-id="159eb-174">Suchen nach bestimmten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="159eb-174">Search for specific events</span></span>
  - <span data-ttu-id="159eb-175">Verwenden Sie die Suchleiste, um nach bestimmten Zeitachsenereignissen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="159eb-175">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="159eb-176">Filtern von Ereignissen anhand eines bestimmten Datums</span><span class="sxs-lookup"><span data-stu-id="159eb-176">Filter events from a specific date</span></span>
  - <span data-ttu-id="159eb-177">Wählen Sie oben links in der Tabelle das Kalendersymbol aus, um Ereignisse des letzten Tags, der letzten Woche, der 30 Tage oder des benutzerdefinierten Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="159eb-177">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="159eb-178">Standardmäßig ist die Gerätezeitachse so festgelegt, dass die Ereignisse aus den letzten 30 Tagen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="159eb-178">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="159eb-179">Verwenden Sie die Zeitachse, um zu einem bestimmten Zeitpunkt zu springen, indem Sie den Abschnitt hervorheben.</span><span class="sxs-lookup"><span data-stu-id="159eb-179">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="159eb-180">Die Pfeile auf der Zeitachse zeigen automatisierte Untersuchungen an.</span><span class="sxs-lookup"><span data-stu-id="159eb-180">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="159eb-181">Exportieren detaillierter Gerätezeitachsenereignisse</span><span class="sxs-lookup"><span data-stu-id="159eb-181">Export detailed device timeline events</span></span>
  - <span data-ttu-id="159eb-182">Exportieren Sie die Gerätezeitachse für das aktuelle Datum oder einen angegebenen Datumsbereich bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="159eb-182">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="159eb-183">Weitere Informationen zu bestimmten Ereignissen finden Sie im Abschnitt **"Zusätzliche Informationen".**</span><span class="sxs-lookup"><span data-stu-id="159eb-183">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="159eb-184">Diese Details variieren je nach Ereignistyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="159eb-184">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="159eb-185">In Application Guard enthalten – das Webbrowserereignis wurde durch einen isolierten Container eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="159eb-185">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="159eb-186">Aktive Bedrohung erkannt – Die Bedrohungserkennung ist aufgetreten, während die Bedrohung ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="159eb-186">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="159eb-187">Problembehebung nicht erfolgreich : Ein Versuch, die erkannte Bedrohung zu beheben, wurde aufgerufen, aber fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="159eb-187">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="159eb-188">Behebung erfolgreich – die erkannte Bedrohung wurde beendet und bereinigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-188">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="159eb-189">Warnung, die vom Benutzer umgangen wird – die Windows Defender SmartScreen-Warnung wurde von einem Benutzer geschlossen und überschrieben.</span><span class="sxs-lookup"><span data-stu-id="159eb-189">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="159eb-190">Verdächtiges Skript erkannt – es wurde ein potenziell schädliches Skript gefunden, das ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="159eb-190">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="159eb-191">Die Warnungskategorie – wenn das Ereignis zur Generierung einer Warnung geführt hat, wird die Warnungskategorie ("Lateral Movement" (z. B. Lateral Movement) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="159eb-191">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="159eb-192">Ereignisdetails</span><span class="sxs-lookup"><span data-stu-id="159eb-192">Event details</span></span>
<span data-ttu-id="159eb-193">Wählen Sie ein Ereignis aus, um relevante Details zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="159eb-193">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="159eb-194">Ein Bereich wird angezeigt, um allgemeine Ereignisinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="159eb-194">A panel displays to show general event information.</span></span> <span data-ttu-id="159eb-195">Wenn zutreffend und Daten verfügbar sind, wird auch ein Diagramm mit verwandten Entitäten und deren Beziehungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-195">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="159eb-196">Um das Ereignis und verwandte Ereignisse weiter zu untersuchen, können Sie schnell eine [erweiterte Suchabfrage](advanced-hunting-overview.md) ausführen, indem Sie **"Suche nach verwandten Ereignissen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="159eb-196">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="159eb-197">Die Abfrage gibt das ausgewählte Ereignis und die Liste der anderen Ereignisse zurück, die ungefähr zur gleichen Zeit auf demselben Endpunkt aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-197">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Abbildung des Bereichs "Ereignisdetails"](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="159eb-199">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="159eb-199">Security recommendations</span></span>

<span data-ttu-id="159eb-200">**Sicherheitsempfehlungen** werden aus der [Funktion "Bedrohungs- & Sicherheitsrisikoverwaltung"](tvm-dashboard-insights.md) von Microsoft Defender für Endpunkt generiert.</span><span class="sxs-lookup"><span data-stu-id="159eb-200">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="159eb-201">Wenn Sie eine Empfehlung auswählen, wird ein Panel angezeigt, in dem Sie relevante Details anzeigen können, z. B. eine Beschreibung der Empfehlung und die potenziellen Risiken, die mit der Nichtersetzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-201">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="159eb-202">Weitere Informationen finden Sie in der [Sicherheitsempfehlung.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-202">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Abbildung der Registerkarte "Sicherheitsempfehlungen"](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="159eb-204">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="159eb-204">Software inventory</span></span>

<span data-ttu-id="159eb-205">Auf der Registerkarte **"Softwareinventur"** können Sie Software auf dem Gerät zusammen mit etwaigen Schwachstellen oder Bedrohungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="159eb-205">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="159eb-206">Wenn Sie den Namen der Software auswählen, gelangen Sie zur Seite "Softwaredetails", auf der Sie Sicherheitsempfehlungen, ermittelte Sicherheitsrisiken, installierte Geräte und Versionsverteilung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="159eb-206">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="159eb-207">Weitere Informationen finden Sie [unter "Softwareinventur"](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-207">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Abbildung der Registerkarte "Softwareinventur"](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="159eb-209">Ermittelte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="159eb-209">Discovered vulnerabilities</span></span>

<span data-ttu-id="159eb-210">Auf der Registerkarte **"Ermittelte Sicherheitsrisiken" werden** der Name, der Schweregrad und die Bedrohungserkenntnisse der entdeckten Sicherheitsrisiken auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-210">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="159eb-211">Wenn Sie bestimmte Sicherheitsrisiken auswählen, werden eine Beschreibung und Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="159eb-211">Selecting specific vulnerabilities will show a description and details.</span></span>

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken"](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="159eb-213">Fehlende KBs</span><span class="sxs-lookup"><span data-stu-id="159eb-213">Missing KBs</span></span>
<span data-ttu-id="159eb-214">Auf der Registerkarte **"Fehlende KBs"** sind die fehlenden Sicherheitsupdates für das Gerät aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="159eb-214">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Abbildung der fehlenden Kbs-Registerkarte](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="159eb-216">Karten</span><span class="sxs-lookup"><span data-stu-id="159eb-216">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="159eb-217">Aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="159eb-217">Active alerts</span></span>

<span data-ttu-id="159eb-218">Die **Azure Advanced Threat Protection-Karte** zeigt eine allgemeine Übersicht über Warnungen im Zusammenhang mit dem Gerät und deren Risikostufe an, wenn Sie das Microsoft Defender for Identity-Feature aktiviert haben und aktive Warnungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-218">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="159eb-219">Weitere Informationen finden Sie im Drilldown "Warnungen".</span><span class="sxs-lookup"><span data-stu-id="159eb-219">More information is available in the "Alerts" drill down.</span></span>

![Abbildung der karte für aktive Warnungen](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="159eb-221">Sie müssen die Integration sowohl in Microsoft Defender for Identity als auch in Defender für Endpunkt aktivieren, um dieses Feature zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="159eb-221">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="159eb-222">In Defender für Endpunkt können Sie dieses Feature in erweiterten Features aktivieren.</span><span class="sxs-lookup"><span data-stu-id="159eb-222">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="159eb-223">Weitere Informationen zum Aktivieren erweiterter Features finden Sie unter [Aktivieren erweiterter Features.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-223">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="159eb-224">Angemeldete Benutzer</span><span class="sxs-lookup"><span data-stu-id="159eb-224">Logged on users</span></span>

<span data-ttu-id="159eb-225">Die Karte **"Angemeldete Benutzer"** zeigt, wie viele Benutzer sich in den letzten 30 Tagen angemeldet haben, zusammen mit den am häufigsten verwendeten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="159eb-225">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="159eb-226">Durch Auswählen des Links "Alle Benutzer anzeigen" wird der Detailbereich geöffnet, in dem Informationen wie Benutzertyp, Anmeldetyp und Wann der Benutzer zum ersten und letzten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="159eb-226">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="159eb-227">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="159eb-227">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Abbildung des Bereichs "Benutzerdetails"](images/logged-on-users.png)
> [!NOTE]
> <span data-ttu-id="159eb-229">Der Wert "Häufigster" Benutzer wird nur auf der Grundlage von Nachweisen von Benutzern berechnet, die sich erfolgreich interaktiv angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="159eb-229">The 'Most frequent' user value is calculated only based on evidence of users who successfully logged on interactively.</span></span> <span data-ttu-id="159eb-230">Der Seitenbereich "Alle Benutzer" berechnet jedoch alle Arten von Benutzeranmeldungen, sodass erwartet wird, dass häufigere Benutzer im Seitenbereich angezeigt werden, da diese Benutzer möglicherweise nicht interaktiv sind.</span><span class="sxs-lookup"><span data-stu-id="159eb-230">However, the "All users" side-pane calculates all sorts of user logons so it is expected to see more frequent users in the side-pane, given that those users may not be interactive.</span></span>

### <a name="security-assessments"></a><span data-ttu-id="159eb-231">Sicherheitsbewertungen</span><span class="sxs-lookup"><span data-stu-id="159eb-231">Security assessments</span></span>

<span data-ttu-id="159eb-232">Die **Karte "Sicherheitsbewertungen"** zeigt die Gesamtbelichtungsstufe, Sicherheitsempfehlungen, installierte Software und ermittelte Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="159eb-232">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="159eb-233">Die Belichtungsstufe eines Geräts wird durch die kumulativen Auswirkungen der ausstehenden Sicherheitsempfehlungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="159eb-233">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Abbildung der Karte für Sicherheitsbewertungen](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="159eb-235">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="159eb-235">Related topics</span></span>

- [<span data-ttu-id="159eb-236">Anzeigen und Organisieren der Warnungswarteschlange für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="159eb-236">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="159eb-237">Verwalten von Microsoft Defender für Endpunkt-Warnungen</span><span class="sxs-lookup"><span data-stu-id="159eb-237">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="159eb-238">Untersuchen von Microsoft Defender für Endpunkt-Warnungen</span><span class="sxs-lookup"><span data-stu-id="159eb-238">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="159eb-239">Untersuchen einer Datei, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="159eb-239">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="159eb-240">Untersuchen einer IP-Adresse, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="159eb-240">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="159eb-241">Untersuchen einer Domäne, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="159eb-241">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="159eb-242">Untersuchen eines Benutzerkontos in Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="159eb-242">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="159eb-243">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="159eb-243">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="159eb-244">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="159eb-244">Software inventory</span></span>](tvm-software-inventory.md)

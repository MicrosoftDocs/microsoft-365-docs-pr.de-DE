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
ms.openlocfilehash: e64f17f2bedea89db1190e6c758c514f14fc3a68
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843578"
---
# <a name="investigate-devices-in-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="65aa8-104">Untersuchen von Geräten in der Liste "Microsoft Defender für Endpunktgeräte"</span><span class="sxs-lookup"><span data-stu-id="65aa8-104">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="65aa8-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="65aa8-105">**Applies to:**</span></span>
- [<span data-ttu-id="65aa8-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="65aa8-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="65aa8-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="65aa8-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="65aa8-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="65aa8-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="65aa8-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="65aa8-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="65aa8-110">Untersuchen Sie die Details einer Warnung, die auf einem bestimmten Gerät ausgelöst wird, um andere Verhaltensweisen oder Ereignisse zu identifizieren, die mit der Warnung oder dem potenziellen Umfang der Verletzung zusammenhängen könnten.</span><span class="sxs-lookup"><span data-stu-id="65aa8-110">Investigate the details of an alert raised on a specific device to identify other behaviors or events that might be related to the alert or the potential scope of the breach.</span></span>

> [!NOTE]
> <span data-ttu-id="65aa8-111">Im Rahmen des Untersuchungs- oder Reaktionsprozesses können Sie ein Untersuchungspaket von einem Gerät erfassen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-111">As part of the investigation or response process, you can collect an investigation package from a device.</span></span> <span data-ttu-id="65aa8-112">Hier sehen Sie, wie: [Erfassen Sie untersuchungspaket von Geräten](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span><span class="sxs-lookup"><span data-stu-id="65aa8-112">Here's how: [Collect investigation package from devices](/microsoft-365/security/defender-endpoint/respond-machine-alerts#collect-investigation-package-from-devices).</span></span>

<span data-ttu-id="65aa8-113">Sie können auf betroffene Geräte klicken, wenn sie im Portal angezeigt werden, um einen detaillierten Bericht zu diesem Gerät zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-113">You can click on affected devices whenever you see them in the portal to open a detailed report about that device.</span></span> <span data-ttu-id="65aa8-114">Betroffene Geräte werden in den folgenden Bereichen identifiziert:</span><span class="sxs-lookup"><span data-stu-id="65aa8-114">Affected devices are identified in the following areas:</span></span>

- [<span data-ttu-id="65aa8-115">Geräteliste</span><span class="sxs-lookup"><span data-stu-id="65aa8-115">Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="65aa8-116">Benachrichtigungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="65aa8-116">Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="65aa8-117">Dashboard für Sicherheitsvorgänge</span><span class="sxs-lookup"><span data-stu-id="65aa8-117">Security operations dashboard</span></span>](security-operations-dashboard.md)
- <span data-ttu-id="65aa8-118">Jede einzelne Warnung</span><span class="sxs-lookup"><span data-stu-id="65aa8-118">Any individual alert</span></span>
- <span data-ttu-id="65aa8-119">Jede einzelne Dateidetailseansicht</span><span class="sxs-lookup"><span data-stu-id="65aa8-119">Any individual file details view</span></span>
- <span data-ttu-id="65aa8-120">Alle IP-Adressen oder Domänendetails</span><span class="sxs-lookup"><span data-stu-id="65aa8-120">Any IP address or domain details view</span></span>

<span data-ttu-id="65aa8-121">Wenn Sie ein bestimmtes Gerät untersuchen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="65aa8-121">When you investigate a specific device, you'll see:</span></span>

- <span data-ttu-id="65aa8-122">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="65aa8-122">Device details</span></span>
- <span data-ttu-id="65aa8-123">Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="65aa8-123">Response actions</span></span>
- <span data-ttu-id="65aa8-124">Registerkarten (Übersicht, Warnungen, Zeitachse, Sicherheitsempfehlungen, Softwareinventarisierung, erkannte Sicherheitsrisiken, fehlende KBs)</span><span class="sxs-lookup"><span data-stu-id="65aa8-124">Tabs (overview, alerts, timeline, security recommendations, software inventory, discovered vulnerabilities, missing KBs)</span></span>
- <span data-ttu-id="65aa8-125">Karten (aktive Warnungen, angemeldete Benutzer, Sicherheitsbewertung)</span><span class="sxs-lookup"><span data-stu-id="65aa8-125">Cards (active alerts, logged on users, security assessment)</span></span>

![Abbildung der Geräteansicht](images/specific-device.png)

## <a name="device-details"></a><span data-ttu-id="65aa8-127">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="65aa8-127">Device details</span></span>

<span data-ttu-id="65aa8-128">Der Abschnitt "Gerätedetails" enthält Informationen wie Domäne, Betriebssystem und Integritätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="65aa8-128">The device details section provides information such as the domain, OS, and health state of the device.</span></span> <span data-ttu-id="65aa8-129">Wenn ein Untersuchungspaket auf dem Gerät verfügbar ist, wird ein Link angezeigt, über den Sie das Paket herunterladen können.</span><span class="sxs-lookup"><span data-stu-id="65aa8-129">If there's an investigation package available on the device, you'll see a link that allows you to download the package.</span></span>

## <a name="response-actions"></a><span data-ttu-id="65aa8-130">Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="65aa8-130">Response actions</span></span>

<span data-ttu-id="65aa8-131">Antwortaktionen werden oben auf einer bestimmten Geräteseite ausgeführt und umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="65aa8-131">Response actions run along the top of a specific device page and include:</span></span>

- <span data-ttu-id="65aa8-132">Verwalten von Kategorien</span><span class="sxs-lookup"><span data-stu-id="65aa8-132">Manage tags</span></span>
- <span data-ttu-id="65aa8-133">Gerät isolieren</span><span class="sxs-lookup"><span data-stu-id="65aa8-133">Isolate device</span></span>
- <span data-ttu-id="65aa8-134">Einschränken der App-Ausführung</span><span class="sxs-lookup"><span data-stu-id="65aa8-134">Restrict app execution</span></span>
- <span data-ttu-id="65aa8-135">Antivirusscan ausführen</span><span class="sxs-lookup"><span data-stu-id="65aa8-135">Run antivirus scan</span></span>
- <span data-ttu-id="65aa8-136">Untersuchungspaket sammeln</span><span class="sxs-lookup"><span data-stu-id="65aa8-136">Collect investigation package</span></span>
- <span data-ttu-id="65aa8-137">Initiieren einer Liveantwortsitzung</span><span class="sxs-lookup"><span data-stu-id="65aa8-137">Initiate Live Response Session</span></span>
- <span data-ttu-id="65aa8-138">Initiieren einer automatisierten Untersuchung</span><span class="sxs-lookup"><span data-stu-id="65aa8-138">Initiate automated investigation</span></span>
- <span data-ttu-id="65aa8-139">Wenden Sie sich an einen Bedrohungsexperten</span><span class="sxs-lookup"><span data-stu-id="65aa8-139">Consult a threat expert</span></span>
- <span data-ttu-id="65aa8-140">Info-Center</span><span class="sxs-lookup"><span data-stu-id="65aa8-140">Action center</span></span>

<span data-ttu-id="65aa8-141">Sie können Reaktionsaktionen im Info-Center, auf einer bestimmten Geräteseite oder auf einer bestimmten Dateiseite ausführen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-141">You can take response actions in the Action center, in a specific device page, or in a specific file page.</span></span>

<span data-ttu-id="65aa8-142">Weitere Informationen zum Ausführen von Maßnahmen auf einem Gerät finden Sie unter "Ergreifen von [Gegenmaßnahmen auf einem Gerät".](respond-machine-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-142">For more information on how to take action on a device, see [Take response action on a device](respond-machine-alerts.md).</span></span>

<span data-ttu-id="65aa8-143">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-143">For more information, see [Investigate user entities](investigate-user.md).</span></span>

## <a name="tabs"></a><span data-ttu-id="65aa8-144">Registerkarten</span><span class="sxs-lookup"><span data-stu-id="65aa8-144">Tabs</span></span>

<span data-ttu-id="65aa8-145">Die Registerkarten enthalten relevante Informationen zur Sicherheit und Bedrohungsverhütung im Zusammenhang mit dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="65aa8-145">The tabs provide relevant security and threat prevention information related to the device.</span></span> <span data-ttu-id="65aa8-146">Auf jeder Registerkarte können Sie die angezeigten Spalten anpassen, indem Sie **Spalten** auf der Leiste oberhalb der Spaltenüberschriften anpassen auswählen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-146">In each tab, you can customize the columns that are shown by selecting **Customize columns** from the bar above the column headers.</span></span>

### <a name="overview"></a><span data-ttu-id="65aa8-147">Übersicht</span><span class="sxs-lookup"><span data-stu-id="65aa8-147">Overview</span></span>
<span data-ttu-id="65aa8-148">Auf der Registerkarte **"Übersicht"** werden die [Karten](#cards) für aktive Warnungen, angemeldete Benutzer und Sicherheitsbewertungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-148">The **Overview** tab displays the [cards](#cards) for active alerts, logged on users, and security assessment.</span></span>

![Abbildung der Registerkarte "Übersicht" auf der Geräteseite](images/overview-device.png)

### <a name="alerts"></a><span data-ttu-id="65aa8-150">Warnungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-150">Alerts</span></span>

<span data-ttu-id="65aa8-151">Die Registerkarte **"Warnungen"** enthält eine Liste der Warnungen, die dem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-151">The **Alerts** tab provides a list of alerts that are associated with the device.</span></span> <span data-ttu-id="65aa8-152">Diese Liste ist eine gefilterte Version der [Warnungswarteschlange](alerts-queue.md)und zeigt eine kurze Beschreibung der Warnung, des Schweregrads (hoch, mittel, niedrig, informational), des Status in der Warteschlange (neu, in Bearbeitung, aufgelöst), der Klassifizierung (nicht festgelegt, falsch, true alert), des Untersuchungsstatus, der Kategorie der Warnung, der Adressierung der Warnung und der letzten Aktivität.</span><span class="sxs-lookup"><span data-stu-id="65aa8-152">This list is a filtered version of the [Alerts queue](alerts-queue.md), and shows a short description of the alert, severity (high, medium, low, informational), status in the queue (new, in progress, resolved), classification (not set, false alert, true alert), investigation state, category of alert, who is addressing the alert, and last activity.</span></span> <span data-ttu-id="65aa8-153">Sie können die Warnungen auch filtern.</span><span class="sxs-lookup"><span data-stu-id="65aa8-153">You can also filter the alerts.</span></span>

![Abbildung von Warnungen im Zusammenhang mit dem Gerät](images/alerts-device.png)

<span data-ttu-id="65aa8-155">Wenn das Kreissymbol links neben einer Warnung ausgewählt ist, wird ein Flyout angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-155">When the circle icon to the left of an alert is selected, a fly-out appears.</span></span> <span data-ttu-id="65aa8-156">In diesem Bereich können Sie die Warnung verwalten und weitere Details wie die Vorfallnummer und verwandte Geräte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-156">From this panel you can manage the alert and view more details such as incident number and related devices.</span></span> <span data-ttu-id="65aa8-157">Mehrere Warnungen können gleichzeitig ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="65aa8-157">Multiple alerts can be selected at a time.</span></span>

<span data-ttu-id="65aa8-158">Um eine vollständige Seitenansicht einer Warnung einschließlich Vorfalldiagramm und Prozessstruktur anzuzeigen, wählen Sie den Titel der Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="65aa8-158">To see a full page view of an alert including incident graph and process tree, select the title of the alert.</span></span>

### <a name="timeline"></a><span data-ttu-id="65aa8-159">Zeitachse</span><span class="sxs-lookup"><span data-stu-id="65aa8-159">Timeline</span></span>

<span data-ttu-id="65aa8-160">Die Registerkarte **"Zeitachse"** bietet eine chronologische Ansicht der Ereignisse und zugehörigen Warnungen, die auf dem Gerät beobachtet wurden.</span><span class="sxs-lookup"><span data-stu-id="65aa8-160">The **Timeline** tab provides a chronological view of the events and associated alerts that have been observed on the device.</span></span> <span data-ttu-id="65aa8-161">Dies kann Ihnen dabei helfen, ereignisse, Dateien und IP-Adressen in Bezug auf das Gerät zu korrelieren.</span><span class="sxs-lookup"><span data-stu-id="65aa8-161">This can help you correlate any events, files, and IP addresses in relation to the device.</span></span>

<span data-ttu-id="65aa8-162">Auf der Zeitachse können Sie auch selektiv Einen Drilldown zu Ereignissen ausführen, die innerhalb eines bestimmten Zeitraums aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-162">The timeline also enables you to selectively drill down into events that occurred within a given time period.</span></span> <span data-ttu-id="65aa8-163">Sie können die zeitliche Abfolge von Ereignissen anzeigen, die über einen ausgewählten Zeitraum auf einem Gerät aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-163">You can view the temporal sequence of events that occurred on a device over a selected time period.</span></span> <span data-ttu-id="65aa8-164">Um die Ansicht weiter zu steuern, können Sie nach Ereignisgruppen filtern oder die Spalten anpassen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-164">To further control your view, you can filter by event groups or customize the columns.</span></span>

>[!NOTE]
> <span data-ttu-id="65aa8-165">Zum Anzeigen von Firewallereignissen müssen Sie die Überwachungsrichtlinie aktivieren. Weitere Informationen finden Sie unter ["Audit Filtering Platform connection".](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)</span><span class="sxs-lookup"><span data-stu-id="65aa8-165">For firewall events to be displayed, you'll need to enable the audit policy, see [Audit Filtering Platform connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection).</span></span>
><span data-ttu-id="65aa8-166">Firewall deckt die folgenden Ereignisse ab</span><span class="sxs-lookup"><span data-stu-id="65aa8-166">Firewall covers the following events</span></span>
>
>- <span data-ttu-id="65aa8-167">[5025](/windows/security/threat-protection/auditing/event-5025) – Firewalldienst beendet</span><span class="sxs-lookup"><span data-stu-id="65aa8-167">[5025](/windows/security/threat-protection/auditing/event-5025) - firewall service stopped</span></span>
>- <span data-ttu-id="65aa8-168">[5031](/windows/security/threat-protection/auditing/event-5031) – Anwendung, die am Akzeptieren eingehender Verbindungen im Netzwerk gehindert wird</span><span class="sxs-lookup"><span data-stu-id="65aa8-168">[5031](/windows/security/threat-protection/auditing/event-5031) - application blocked from accepting incoming connections on the network</span></span>
>- <span data-ttu-id="65aa8-169">[5157 –](/windows/security/threat-protection/auditing/event-5157) blockierte Verbindung</span><span class="sxs-lookup"><span data-stu-id="65aa8-169">[5157](/windows/security/threat-protection/auditing/event-5157) - blocked connection</span></span>

![Abbildung der Gerätezeitachse mit Ereignissen](images/timeline-device.png)

<span data-ttu-id="65aa8-171">Einige der Funktionen umfassen:</span><span class="sxs-lookup"><span data-stu-id="65aa8-171">Some of the functionality includes:</span></span>

- <span data-ttu-id="65aa8-172">Suchen nach bestimmten Ereignissen</span><span class="sxs-lookup"><span data-stu-id="65aa8-172">Search for specific events</span></span>
  - <span data-ttu-id="65aa8-173">Verwenden Sie die Suchleiste, um nach bestimmten Zeitachsenereignissen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-173">Use the search bar to look for specific timeline events.</span></span>
- <span data-ttu-id="65aa8-174">Filtern von Ereignissen anhand eines bestimmten Datums</span><span class="sxs-lookup"><span data-stu-id="65aa8-174">Filter events from a specific date</span></span>
  - <span data-ttu-id="65aa8-175">Wählen Sie oben links in der Tabelle das Kalendersymbol aus, um Ereignisse des letzten Tags, der letzten Woche, der 30 Tage oder des benutzerdefinierten Bereichs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-175">Select the calendar icon in the upper left of the table to display events in the past day, week, 30 days, or custom range.</span></span> <span data-ttu-id="65aa8-176">Standardmäßig ist die Gerätezeitachse so festgelegt, dass die Ereignisse aus den letzten 30 Tagen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="65aa8-176">By default, the device timeline is set to display the events from the past 30 days.</span></span>
  - <span data-ttu-id="65aa8-177">Verwenden Sie die Zeitachse, um zu einem bestimmten Zeitpunkt zu springen, indem Sie den Abschnitt hervorheben.</span><span class="sxs-lookup"><span data-stu-id="65aa8-177">Use the timeline to jump to a specific moment in time by highlighting the section.</span></span> <span data-ttu-id="65aa8-178">Die Pfeile auf der Zeitachse zeigen automatisierte Untersuchungen an.</span><span class="sxs-lookup"><span data-stu-id="65aa8-178">The arrows on the timeline pinpoint automated investigations</span></span>
- <span data-ttu-id="65aa8-179">Exportieren detaillierter Gerätezeitachsenereignisse</span><span class="sxs-lookup"><span data-stu-id="65aa8-179">Export detailed device timeline events</span></span>
  - <span data-ttu-id="65aa8-180">Exportieren Sie die Gerätezeitachse für das aktuelle Datum oder einen angegebenen Datumsbereich bis zu sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="65aa8-180">Export the device timeline for the current date or a specified date range up to seven days.</span></span>

<span data-ttu-id="65aa8-181">Weitere Informationen zu bestimmten Ereignissen finden Sie im Abschnitt **"Zusätzliche Informationen".**</span><span class="sxs-lookup"><span data-stu-id="65aa8-181">More details about certain events are provided in the **Additional information** section.</span></span> <span data-ttu-id="65aa8-182">Diese Details variieren je nach Ereignistyp, z. B.:</span><span class="sxs-lookup"><span data-stu-id="65aa8-182">These details vary depending on the type of event, for example:</span></span> 

- <span data-ttu-id="65aa8-183">In Application Guard enthalten – das Webbrowserereignis wurde durch einen isolierten Container eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-183">Contained by Application Guard - the web browser event was restricted by an isolated container</span></span>
- <span data-ttu-id="65aa8-184">Aktive Bedrohung erkannt – Die Bedrohungserkennung ist aufgetreten, während die Bedrohung ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="65aa8-184">Active threat detected - the threat detection occurred while the threat was running</span></span>
- <span data-ttu-id="65aa8-185">Problembehebung nicht erfolgreich : Ein Versuch, die erkannte Bedrohung zu beheben, wurde aufgerufen, aber fehlgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-185">Remediation unsuccessful - an attempt to remediate the detected threat was invoked but failed</span></span>
- <span data-ttu-id="65aa8-186">Behebung erfolgreich – die erkannte Bedrohung wurde beendet und bereinigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-186">Remediation successful - the detected threat was stopped and cleaned</span></span>
- <span data-ttu-id="65aa8-187">Warnung, die vom Benutzer umgangen wird – die Windows Defender SmartScreen-Warnung wurde von einem Benutzer geschlossen und überschrieben.</span><span class="sxs-lookup"><span data-stu-id="65aa8-187">Warning bypassed by user - the Windows Defender SmartScreen warning was dismissed and overridden by a user</span></span>
- <span data-ttu-id="65aa8-188">Verdächtiges Skript erkannt – es wurde ein potenziell schädliches Skript gefunden, das ausgeführt wurde</span><span class="sxs-lookup"><span data-stu-id="65aa8-188">Suspicious script detected - a potentially malicious script was found running</span></span>
- <span data-ttu-id="65aa8-189">Die Warnungskategorie – wenn das Ereignis zur Generierung einer Warnung geführt hat, wird die Warnungskategorie ("Lateral Movement" (z. B. Lateral Movement) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-189">The alert category - if the event led to the generation of an alert, the alert category  ("Lateral Movement", for example) is provided</span></span>

#### <a name="event-details"></a><span data-ttu-id="65aa8-190">Ereignisdetails</span><span class="sxs-lookup"><span data-stu-id="65aa8-190">Event details</span></span>
<span data-ttu-id="65aa8-191">Wählen Sie ein Ereignis aus, um relevante Details zu diesem Ereignis anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-191">Select an event to view relevant details about that event.</span></span> <span data-ttu-id="65aa8-192">Ein Bereich wird angezeigt, um allgemeine Ereignisinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-192">A panel displays to show general event information.</span></span> <span data-ttu-id="65aa8-193">Wenn zutreffend und Daten verfügbar sind, wird auch ein Diagramm mit verwandten Entitäten und deren Beziehungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-193">When applicable and data is available, a graph showing related entities and their relationships are also shown.</span></span>

<span data-ttu-id="65aa8-194">Um das Ereignis und verwandte Ereignisse weiter zu untersuchen, können Sie schnell eine [erweiterte Suchabfrage](advanced-hunting-overview.md) ausführen, indem Sie **"Suche nach verwandten Ereignissen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-194">To further inspect the event and related events, you can quickly run an [advanced hunting](advanced-hunting-overview.md) query by selecting **Hunt for related events**.</span></span> <span data-ttu-id="65aa8-195">Die Abfrage gibt das ausgewählte Ereignis und die Liste der anderen Ereignisse zurück, die ungefähr zur gleichen Zeit auf demselben Endpunkt aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-195">The query will return the selected event and the list of other events that occurred around the same time on the same endpoint.</span></span>

![Abbildung des Bereichs "Ereignisdetails"](images/event-details.png)

### <a name="security-recommendations"></a><span data-ttu-id="65aa8-197">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-197">Security recommendations</span></span>

<span data-ttu-id="65aa8-198">**Sicherheitsempfehlungen** werden aus der [Funktion "Bedrohungs- & Sicherheitsrisikoverwaltung"](tvm-dashboard-insights.md) von Microsoft Defender für Endpunkt generiert.</span><span class="sxs-lookup"><span data-stu-id="65aa8-198">**Security recommendations** are generated from Microsoft Defender for Endpoint's [Threat & Vulnerability Management](tvm-dashboard-insights.md) capability.</span></span> <span data-ttu-id="65aa8-199">Wenn Sie eine Empfehlung auswählen, wird ein Panel angezeigt, in dem Sie relevante Details anzeigen können, z. B. eine Beschreibung der Empfehlung und die potenziellen Risiken, die mit der Nichtersetzung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-199">Selecting a recommendation will show a panel where you can view relevant details such as description of the recommendation and the potential risks associated with not enacting it.</span></span> <span data-ttu-id="65aa8-200">Weitere Informationen finden Sie in der [Sicherheitsempfehlung.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-200">See [Security recommendation](tvm-security-recommendation.md) for details.</span></span>

![Abbildung der Registerkarte "Sicherheitsempfehlungen"](images/security-recommendations-device.png)

### <a name="software-inventory"></a><span data-ttu-id="65aa8-202">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="65aa8-202">Software inventory</span></span>

<span data-ttu-id="65aa8-203">Auf der Registerkarte **"Softwareinventur"** können Sie Software auf dem Gerät zusammen mit etwaigen Schwachstellen oder Bedrohungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="65aa8-203">The **Software inventory** tab lets you view software on the device, along with any weaknesses or threats.</span></span> <span data-ttu-id="65aa8-204">Wenn Sie den Namen der Software auswählen, gelangen Sie zur Seite "Softwaredetails", auf der Sie Sicherheitsempfehlungen, ermittelte Sicherheitsrisiken, installierte Geräte und Versionsverteilung anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="65aa8-204">Selecting the name of the software will take you to the software details page where you can view security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span> <span data-ttu-id="65aa8-205">Weitere Informationen finden Sie [unter "Softwareinventur"](tvm-software-inventory.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-205">See [Software inventory](tvm-software-inventory.md) for details</span></span>

![Abbildung der Registerkarte "Softwareinventur"](images/software-inventory-device.png)

### <a name="discovered-vulnerabilities"></a><span data-ttu-id="65aa8-207">Ermittelte Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="65aa8-207">Discovered vulnerabilities</span></span>

<span data-ttu-id="65aa8-208">Auf der Registerkarte **"Ermittelte Sicherheitsrisiken" werden** der Name, der Schweregrad und die Bedrohungserkenntnisse der entdeckten Sicherheitsrisiken auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-208">The **Discovered vulnerabilities** tab shows the name, severity, and threat insights of discovered vulnerabilities on the device.</span></span> <span data-ttu-id="65aa8-209">Wenn Sie bestimmte Sicherheitsrisiken auswählen, werden eine Beschreibung und Details angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-209">Selecting specific vulnerabilities will show a description and details.</span></span>

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken"](images/discovered-vulnerabilities-device.png)

### <a name="missing-kbs"></a><span data-ttu-id="65aa8-211">Fehlende KBs</span><span class="sxs-lookup"><span data-stu-id="65aa8-211">Missing KBs</span></span>
<span data-ttu-id="65aa8-212">Auf der Registerkarte **"Fehlende KBs"** sind die fehlenden Sicherheitsupdates für das Gerät aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-212">The **Missing KBs** tab lists the missing security updates for the device.</span></span>

![Abbildung der fehlenden Kbs-Registerkarte](images/missing-kbs-device.png)

## <a name="cards"></a><span data-ttu-id="65aa8-214">Karten</span><span class="sxs-lookup"><span data-stu-id="65aa8-214">Cards</span></span>

### <a name="active-alerts"></a><span data-ttu-id="65aa8-215">Aktive Warnungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-215">Active alerts</span></span>

<span data-ttu-id="65aa8-216">Die **Azure Advanced Threat Protection-Karte** zeigt eine allgemeine Übersicht über Warnungen im Zusammenhang mit dem Gerät und deren Risikostufe an, wenn Sie das Microsoft Defender for Identity-Feature aktiviert haben und aktive Warnungen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="65aa8-216">The **Azure Advanced Threat Protection** card will display a high-level overview of alerts related to the device and their risk level, if you have enabled the Microsoft Defender for Identity feature, and there are any active alerts.</span></span> <span data-ttu-id="65aa8-217">Weitere Informationen finden Sie im Drilldown "Warnungen".</span><span class="sxs-lookup"><span data-stu-id="65aa8-217">More information is available in the "Alerts" drill down.</span></span>

![Abbildung der karte für aktive Warnungen](images/risk-level-small.png)

>[!NOTE]
><span data-ttu-id="65aa8-219">Sie müssen die Integration sowohl in Microsoft Defender for Identity als auch in Defender für Endpunkt aktivieren, um dieses Feature zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="65aa8-219">You'll need to enable the integration on both Microsoft Defender for Identity and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="65aa8-220">In Defender für Endpunkt können Sie dieses Feature in erweiterten Features aktivieren.</span><span class="sxs-lookup"><span data-stu-id="65aa8-220">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="65aa8-221">Weitere Informationen zum Aktivieren erweiterter Features finden Sie unter [Aktivieren erweiterter Features.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-221">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

### <a name="logged-on-users"></a><span data-ttu-id="65aa8-222">Angemeldete Benutzer</span><span class="sxs-lookup"><span data-stu-id="65aa8-222">Logged on users</span></span>

<span data-ttu-id="65aa8-223">Die Karte **"Angemeldete Benutzer"** zeigt, wie viele Benutzer sich in den letzten 30 Tagen angemeldet haben, zusammen mit den am häufigsten verwendeten Benutzern.</span><span class="sxs-lookup"><span data-stu-id="65aa8-223">The **Logged on users** card shows how many users have logged on in the past 30 days, along with the most and least frequent users.</span></span> <span data-ttu-id="65aa8-224">Durch Auswählen des Links "Alle Benutzer anzeigen" wird der Detailbereich geöffnet, in dem Informationen wie Benutzertyp, Anmeldetyp und Wann der Benutzer zum ersten und letzten Mal angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="65aa8-224">Selecting the "See all users" link opens the details pane, which displays information such as user type, log on type, and when the user was first and last seen.</span></span> <span data-ttu-id="65aa8-225">Weitere Informationen finden Sie unter [Untersuchen von Benutzerentitäten.](investigate-user.md)</span><span class="sxs-lookup"><span data-stu-id="65aa8-225">For more information, see [Investigate user entities](investigate-user.md).</span></span>

![Abbildung des Bereichs "Benutzerdetails"](images/logged-on-users.png)

### <a name="security-assessments"></a><span data-ttu-id="65aa8-227">Sicherheitsbewertungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-227">Security assessments</span></span>

<span data-ttu-id="65aa8-228">Die **Karte "Sicherheitsbewertungen"** zeigt die Gesamtbelichtungsstufe, Sicherheitsempfehlungen, installierte Software und ermittelte Sicherheitsrisiken.</span><span class="sxs-lookup"><span data-stu-id="65aa8-228">The **Security assessments** card shows the overall exposure level, security recommendations, installed software, and discovered vulnerabilities.</span></span> <span data-ttu-id="65aa8-229">Die Belichtungsstufe eines Geräts wird durch die kumulativen Auswirkungen der ausstehenden Sicherheitsempfehlungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="65aa8-229">A device's exposure level is determined by the cumulative impact of its pending security recommendations.</span></span>

![Abbildung der Karte für Sicherheitsbewertungen](images/security-assessments.png)

## <a name="related-topics"></a><span data-ttu-id="65aa8-231">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="65aa8-231">Related topics</span></span>

- [<span data-ttu-id="65aa8-232">Anzeigen und Organisieren der Microsoft Defender für Endpunkt-Warnungswarteschlange</span><span class="sxs-lookup"><span data-stu-id="65aa8-232">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="65aa8-233">Verwalten von Microsoft Defender für Endpunkt-Warnungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-233">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="65aa8-234">Untersuchen von Microsoft Defender für Endpunkt-Warnungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-234">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="65aa8-235">Untersuchen einer Datei, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="65aa8-235">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="65aa8-236">Untersuchen einer IP-Adresse, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="65aa8-236">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="65aa8-237">Untersuchen einer Domäne, die einer Defender für Endpunkt-Warnung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="65aa8-237">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="65aa8-238">Untersuchen eines Benutzerkontos in Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="65aa8-238">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="65aa8-239">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="65aa8-239">Security recommendation</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="65aa8-240">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="65aa8-240">Software inventory</span></span>](tvm-software-inventory.md)

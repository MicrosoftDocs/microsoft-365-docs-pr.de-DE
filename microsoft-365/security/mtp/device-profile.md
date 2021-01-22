---
title: Geräteprofil im Microsoft 365-Sicherheitsportal
description: Zeigen Sie die Risiko- und Risikostufen für ein Gerät in Ihrer Organisation an. Analysieren Sie vergangene und aktuelle Bedrohungen, und schützen Sie das Gerät mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Security Center, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Geräteseite, Geräteprofil, Computerseite, Computerprofil
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 40897185ab885ee2b6880ecd5f25d95fbe3d771e
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929574"
---
# <a name="device-profile-page"></a><span data-ttu-id="bb5aa-105">Seite "Geräteprofil"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-105">Device profile page</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="bb5aa-106">Das Microsoft 365-Sicherheitsportal stellt Ihnen Geräteprofilseiten zur Verfügung, sodass Sie den Zustand und Status von Geräten in Ihrem Netzwerk schnell bewerten können.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bb5aa-107">Je nachdem, ob das Gerät in Microsoft Defender für Endpoint, Microsoft Defender for Identity oder beides registriert ist, kann die Seite mit dem Geräteprofil etwas anders angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender for Endpoint, Microsoft Defender for Identity, or both.</span></span>

<span data-ttu-id="bb5aa-108">Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, können Sie auch die Geräteprofilseite verwenden, um einige allgemeine Sicherheitsaufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-108">If the device is enrolled in Microsoft Defender for Endpoint, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="bb5aa-109">Navigieren auf der Geräteprofilseite</span><span class="sxs-lookup"><span data-stu-id="bb5aa-109">Navigating the device profile page</span></span>

<span data-ttu-id="bb5aa-110">Die Profilseite ist in mehrere breite Abschnitte unterteilt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-110">The profile page is broken up into several broad sections.</span></span>

![Abbildung der Geräteprofilseite mit (1) Registerkartenbereich (2) Randleiste und (3) Rot hervorgehobenen Aktionen](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="bb5aa-112">In der Randleiste (1) sind grundlegende Details zum Gerät aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="bb5aa-113">Der Hauptinhaltsbereich (2) enthält Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen über das Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="bb5aa-114">Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, wird auch eine Liste der Antwortaktionen (3) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-114">If the device is enrolled in Microsoft Defender for Endpoint, you will also see a list of response actions (3).</span></span> <span data-ttu-id="bb5aa-115">Mit Reaktionsaktionen können Sie allgemeine sicherheitsbezogene Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="bb5aa-116">Randleiste</span><span class="sxs-lookup"><span data-stu-id="bb5aa-116">Sidebar</span></span>

<span data-ttu-id="bb5aa-117">Neben dem Hauptinhaltsbereich der Geräteprofilseite befindet sich die Seitenleiste.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Abbildung der Registerkarte "Sidebar" für das Geräteprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="bb5aa-119">Die Randleiste listet den vollständigen Namen und die Belichtungsstufe des Geräts auf.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="bb5aa-120">Es enthält auch einige wichtige grundlegende Informationen in kleinen Unterabschnitten, die geöffnet oder geschlossen umschalten können, z. B.:</span><span class="sxs-lookup"><span data-stu-id="bb5aa-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="bb5aa-121">**Tags** – Beliebige Microsoft Defender für Endpoint, Microsoft Defender for Identity oder benutzerdefinierte Tags, die dem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-121">**Tags** - Any Microsoft Defender for Endpoint, Microsoft Defender for Identity, or custom tags associated with the device.</span></span> <span data-ttu-id="bb5aa-122">Tags aus Microsoft Defender for Identity können nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-122">Tags from Microsoft Defender for Identity are not editable.</span></span>
* <span data-ttu-id="bb5aa-123">**Sicherheitsinformationen** – Öffnen von Vorfällen und aktiven Warnungen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="bb5aa-124">Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch die Belichtungsstufe und die Risikostufe an.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-124">Devices enrolled in Microsoft Defender for Endpoint will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="bb5aa-125">Die Gefährdungsstufe bezieht sich darauf, wie weit das Gerät sicherheitsempfehlungen entspricht, während die Risikostufe basierend auf einer Reihe von Faktoren berechnet wird, einschließlich der Typen und des Schweregrads aktiver Warnungen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="bb5aa-126">**Gerätedetails** – Domäne, Betriebssystem, Zeitstempel für das erste Anzeigen des Geräts, IP-Adressen, Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="bb5aa-127">Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch den Integritätsstatus an.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-127">Devices enrolled in Microsoft Defender for Endpoint also display health state.</span></span> <span data-ttu-id="bb5aa-128">Geräte, die in Microsoft Defender for Identity registriert sind, zeigen den Namen des Sam und einen Zeitstempel an, als das Gerät zum ersten Mal erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-128">Devices enrolled in Microsoft Defender for Identity will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="bb5aa-129">**Netzwerkaktivität** – Zeitstempel zum ersten und letzten Mal, als das Gerät im Netzwerk gesehen wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="bb5aa-130">**Verzeichnisdaten** ( nur für Geräte, die *in Microsoft Defender for Identity* registriert sind) – [UAC-Flags,](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)und Gruppenmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-130">**Directory data** (*only for devices enrolled in Microsoft Defender for Identity*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="bb5aa-131">Antwortaktionen</span><span class="sxs-lookup"><span data-stu-id="bb5aa-131">Response actions</span></span>

<span data-ttu-id="bb5aa-132">Reaktionsaktionen bieten eine schnelle Möglichkeit, sich vor Bedrohungen zu schützen und sie zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Abbildung der Aktionsleiste für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="bb5aa-134">[Antwortaktionen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sind nur verfügbar, wenn das Gerät in Microsoft Defender for Endpoint registriert ist.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender for Endpoint.</span></span>
> * <span data-ttu-id="bb5aa-135">Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen je nach Betriebssystem und Versionsnummer des Geräts möglicherweise eine unterschiedliche Anzahl von Antwortaktionen an.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-135">Devices that are enrolled in Microsoft Defender for Endpoint may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="bb5aa-136">Auf der Seite "Geräteprofil" sind folgende Aktionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="bb5aa-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="bb5aa-137">**Tags verwalten** – Aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="bb5aa-138">**Gerät isolieren** – Isoliert das Gerät vom Netzwerk Ihrer Organisation, während es mit Microsoft Defender for Endpoint verbunden bleibt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bb5aa-139">Sie können festlegen, dass Outlook, Teams und Skype for Business ausgeführt werden können, während das Gerät isoliert ist, um Kommunikationszwecken zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="bb5aa-140">**Aktionscenter** – Anzeigen des Status der übermittelten Aktionen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="bb5aa-141">Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="bb5aa-142">**Einschränken der App-Ausführung:** Verhindert die Ausführung von Anwendungen, die nicht von Microsoft signiert sind.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="bb5aa-143">**Ausführen eines Antivirenscans** – Updates Windows Defender Antivirusdefinitionen und führen sofort einen Antivirenscan aus.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="bb5aa-144">Wählen Sie zwischen Schnellscan oder vollständiger Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="bb5aa-145">**Untersuchungspaket sammeln** – Sammelt Informationen über das Gerät.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="bb5aa-146">Wenn die Untersuchung abgeschlossen ist, können Sie sie herunterladen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="bb5aa-147">**Initiieren einer Liveantwortsitzung** – Lädt eine Remoteshell auf dem Gerät für [eingehende Sicherheitsuntersuchungen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)</span><span class="sxs-lookup"><span data-stu-id="bb5aa-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="bb5aa-148">**Initiieren einer automatisierten** Untersuchung [– Bedrohungen werden automatisch](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)untersucht und behoben.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="bb5aa-149">Sie können zwar automatisierte Untersuchungen manuell von dieser Seite aus [auslösen,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) bestimmte Warnungsrichtlinien lösen jedoch selbst automatische Untersuchungen aus.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="bb5aa-150">**Info-Center:** Zeigt Informationen zu allen Derzeit ausgeführten Antwortaktionen an.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="bb5aa-151">Tabs section</span><span class="sxs-lookup"><span data-stu-id="bb5aa-151">Tabs section</span></span>

<span data-ttu-id="bb5aa-152">Auf den Registerkarten des Geräteprofils können Sie eine Übersicht über Sicherheitsdetails zum Gerät und Tabellen mit einer Liste von Warnungen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="bb5aa-153">Geräte, die in Microsoft Defender for Endpoint registriert sind, zeigen auch Registerkarten an, die eine Zeitachse, eine Liste von Sicherheitsempfehlungen, ein Softwareinventar, eine Liste der ermittelten Sicherheitsrisiken und fehlende KBs (Sicherheitsupdates) enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-153">Devices enrolled in Microsoft Defender for Endpoint will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="bb5aa-154">Registerkarte "Übersicht"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-154">Overview tab</span></span>

<span data-ttu-id="bb5aa-155">Die Standardregisterkarte ist **Übersicht**.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-155">The default tab is **Overview**.</span></span> <span data-ttu-id="bb5aa-156">Es bietet einen schnellen Überblick über die wichtigsten Sicherheitsrisiken des Geräts.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-156">It provides a quick look at the most important security fact about the device.</span></span>

![Abbildung der Registerkarte "Übersicht" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="bb5aa-158">Hier erhalten Sie einen schnellen Überblick über die aktiven Warnungen des Geräts und alle aktuell angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="bb5aa-159">Wenn das Gerät in Microsoft Defender for Endpoint registriert ist, werden auch die Risikostufe des Geräts und alle verfügbaren Daten in Sicherheitsbewertungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-159">If the device is enrolled in Microsoft Defender for Endpoint, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="bb5aa-160">In den Sicherheitsbewertungen wird die Gefährdungsstufe des Geräts beschrieben, Sicherheitsempfehlungen gegeben, betroffene Software und ermittelte Sicherheitsrisiken aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="bb5aa-161">Registerkarte "Warnungen"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-161">Alerts tab</span></span>

<span data-ttu-id="bb5aa-162">Die **Registerkarte** "Warnungen" enthält eine Liste der Warnungen, die auf dem Gerät ausgelöst wurden, sowohl von Microsoft Defender for Identity als auch von Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Microsoft Defender for Identity and Microsoft Defender for Endpoint.</span></span>

![Abbildung der Registerkarte "Warnungen" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="bb5aa-164">Sie können die Anzahl der angezeigten Elemente sowie die Spalten anpassen, die für jedes Element angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="bb5aa-165">Standardmäßig werden 30 Elemente pro Seite aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="bb5aa-166">Die Spalten auf dieser Registerkarte enthalten Informationen zum Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie Status, Untersuchungsstatus und wem die Warnung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="bb5aa-167">Die *Spalte "Betroffene Entitäten"* bezieht sich auf das Gerät (Entität), dessen Profil Sie gerade anzeigen, sowie alle anderen Geräte in Ihrem Netzwerk, die betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="bb5aa-168">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das noch mehr Informationen zur ausgewählten Warnung enthält.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="bb5aa-169">Diese Liste kann nach Schweregrad, Status oder dem Benutzer gefiltert werden, dem die Warnung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="bb5aa-170">Registerkarte "Zeitachse"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-170">Timeline tab</span></span>

<span data-ttu-id="bb5aa-171">Die **Registerkarte "Zeitachse"** enthält ein interaktives, chronologisches Diagramm aller ereignisse, die auf dem Gerät ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="bb5aa-172">Durch Verschieben des hervorgehobenen Bereichs des Diagramms nach links oder rechts können Sie Ereignisse über verschiedene Zeiträume anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="bb5aa-173">Sie können auch einen benutzerdefinierten Datumsbereich aus dem Dropdownmenü zwischen dem interaktiven Diagramm und der Ereignisliste auswählen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="bb5aa-174">Unterhalb des Diagramms befindet sich eine Liste der Ereignisse für den ausgewählten Datumsbereich.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Abbildung der Registerkarte "Zeitachse" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="bb5aa-176">Die Anzahl der angezeigten Elemente und die Spalten in der Liste können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="bb5aa-177">Die Standardspalten enthalten die Ereigniszeit, den aktiven Benutzer, den Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="bb5aa-178">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem ein Diagramm mit Ereignisentitäten angezeigt wird, in dem die übergeordneten und untergeordneten Prozesse des Ereignisses angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="bb5aa-179">Die Liste kann nach dem jeweiligen Ereignistyp gefiltert werden. z. B. Registrierungsereignisse oder Smart screen-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="bb5aa-180">Die Liste kann auch zum Download in eine CSV-Datei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="bb5aa-181">Die Datei ist zwar nicht durch die Anzahl der Ereignisse beschränkt, der maximale Zeitraum, den Sie exportieren können, beträgt jedoch sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="bb5aa-182">Registerkarte "Sicherheitsempfehlungen"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-182">Security recommendations tab</span></span>

<span data-ttu-id="bb5aa-183">Auf **der Registerkarte "Sicherheitsempfehlungen"** sind Aktionen aufgeführt, die Sie zum Schutz des Geräts ergreifen können.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="bb5aa-184">Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen zum Anwenden der Empfehlung erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Abbildung der Registerkarte "Sicherheitsempfehlungen" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="bb5aa-186">Wie bei den vorherigen Registerkarten kann die Anzahl der pro Seite angezeigten Elemente sowie die sichtbaren Spalten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="bb5aa-187">Die Standardansicht enthält Spalten, in der die sicherheitsrelevanten Schwachstellen, die zugeordnete Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen ist, und vieles mehr beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="bb5aa-188">Elemente können nach dem Status der Empfehlung gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="bb5aa-189">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="bb5aa-189">Software inventory</span></span>

<span data-ttu-id="bb5aa-190">Auf **der Registerkarte "Softwareinventar"** wird die auf dem Gerät installierte Software aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Abbildung der Registerkarte "Softwareinventar" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="bb5aa-192">In der Standardansicht werden der Softwareanbieter, die installierte Versionsnummer, die Anzahl bekannter Softwareschwächen, Bedrohungseinblicke, Produktcode und Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="bb5aa-193">Die Anzahl der angezeigten Elemente und die angezeigten Spalten können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="bb5aa-194">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das weitere Details zur ausgewählten Software sowie den Pfad und Zeitstempel für das letzte Mal enthält, als die Software gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="bb5aa-195">Diese Liste kann nach Produktcode gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="bb5aa-196">Registerkarte "Ermittelte Sicherheitsrisiken"</span><span class="sxs-lookup"><span data-stu-id="bb5aa-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="bb5aa-197">Auf **der Registerkarte "Ermittelte Sicherheitsrisiken"** werden alle allgemeinen Sicherheitsrisiken und Exploits (Common Vulnerabilities and Exploits, CVEs) aufgeführt, die sich auf das Gerät auswirken können.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Abbildung der Registerkarte "Ermittelte Sicherheitsrisiken" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="bb5aa-199">In der Standardansicht werden der Schweregrad des CVE, das allgemeine Sicherheitsrisikoergebnis (Common Vulnerability Score, CVS), die Software im Zusammenhang mit dem CVE, der Veröffentlichung des CVE, der letzte Aktualisierung des CVE und bedrohungen im Zusammenhang mit cvE aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="bb5aa-200">Wie bei den vorherigen Registerkarten kann die Anzahl der angezeigten Elemente und die sichtbaren Spalten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="bb5aa-201">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, das den CVE beschreibt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="bb5aa-202">Fehlende KBs</span><span class="sxs-lookup"><span data-stu-id="bb5aa-202">Missing KBs</span></span>

<span data-ttu-id="bb5aa-203">Auf **der Registerkarte "Fehlende KBs"** werden alle Microsoft Updates aufgeführt, die noch auf das Gerät angewendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="bb5aa-204">Bei den "KBs" handelt es sich um [Knowledge Base-Artikel,](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) in denen diese Updates beschrieben werden. Beispiel: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="bb5aa-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Abbildung der Registerkarte "Fehlende KBs" für das Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="bb5aa-206">In der Standardansicht wird das Bulletin mit updates, Betriebssystemversion, betroffenen Produkten, adressierte CVEs, der KB-Nummer und Tags aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="bb5aa-207">Die Anzahl der pro Seite angezeigten Elemente und die angezeigten Spalten können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="bb5aa-208">Wenn Sie ein Element auswählen, wird ein Flyout geöffnet, das mit dem Update verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="bb5aa-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb5aa-209">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="bb5aa-209">Related topics</span></span>

* [<span data-ttu-id="bb5aa-210">Übersicht über Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb5aa-210">Microsoft 365 Defender overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="bb5aa-211">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="bb5aa-211">Turn on Microsoft 365 Defender</span></span>](mtp-enable.md)
* [<span data-ttu-id="bb5aa-212">Untersuchen von Entitäten auf Geräten mithilfe von Liveantworten</span><span class="sxs-lookup"><span data-stu-id="bb5aa-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="bb5aa-213">Automatisierte Untersuchung und Reaktion (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="bb5aa-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)

---
title: Geräteprofil im Microsoft 365-Sicherheitsportal
description: Anzeigen von Risiko-und Expositions Ebenen für ein Gerät in Ihrer Organisation. Analysieren Sie vergangene und gegenwärtige Bedrohungen, und schützen Sie das Gerät mit den neuesten Updates.
keywords: Sicherheit, Schadsoftware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Sicherheitscenter, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Geräteseite, Geräteprofil, Computer Seite, Computer Profil
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: v-maave
author: martyav
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: db6109fb73f0e208ab4403e2469bc955a1a01b38
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "43517037"
---
# <a name="device-profile-page"></a><span data-ttu-id="2f0ca-105">Geräteprofil Seite</span><span class="sxs-lookup"><span data-stu-id="2f0ca-105">Device profile page</span></span>

<span data-ttu-id="2f0ca-106">Das Microsoft 365-Sicherheitsportal bietet Ihnen Geräteprofil Seiten, sodass Sie die Integrität und den Status von Geräten in Ihrem Netzwerk schnell bewerten können.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-106">The Microsoft 365 security portal provides you with device profile pages, so you can quickly assess the health and status of devices on your network.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2f0ca-107">Die Geräteprofil Seite erscheint möglicherweise geringfügig anders, je nachdem, ob das Gerät in Microsoft Defender ATP, Azure ATP oder in beiden registriert ist.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-107">The device profile page may appear slightly different, depending on whether the device is enrolled in Microsoft Defender ATP, Azure ATP, or both.</span></span>

<span data-ttu-id="2f0ca-108">Wenn das Gerät in Microsoft Defender ATP registriert ist, können Sie auch die Geräteprofil Seite verwenden, um einige allgemeine Sicherheitsaufgaben auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-108">If the device is enrolled in Microsoft Defender ATP, you can also use the device profile page to perform some common security tasks.</span></span>

## <a name="navigating-the-device-profile-page"></a><span data-ttu-id="2f0ca-109">Navigieren auf der Geräteprofil Seite</span><span class="sxs-lookup"><span data-stu-id="2f0ca-109">Navigating the device profile page</span></span>

<span data-ttu-id="2f0ca-110">Die Profilseite ist in mehrere allgemeine Abschnitte unterteilt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-110">The profile page is broken up into several broad sections.</span></span>

![Bild der Geräteprofil Seite mit (1) Registerkartenbereich (2) Sidebar und (3) Aktionen in rot hervorgehoben](../../media/mtp-device-profile/hybrid-device-overall.png)

<span data-ttu-id="2f0ca-112">In der Sidebar (1) werden grundlegende Details zum Gerät aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-112">The sidebar (1) lists basic details about the device.</span></span>

<span data-ttu-id="2f0ca-113">Der Hauptinhaltsbereich (2) enthält Registerkarten, die Sie umschalten können, um verschiedene Arten von Informationen zum Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-113">The main content area (2) contains tabs that you can toggle through to view different kinds of information about the device.</span></span>

<span data-ttu-id="2f0ca-114">Wenn das Gerät in Microsoft Defender ATP registriert ist, wird auch eine Liste der Antwort Aktionen angezeigt (3).</span><span class="sxs-lookup"><span data-stu-id="2f0ca-114">If the device is enrolled in Microsoft Defender ATP, you will also see a list of response actions (3).</span></span> <span data-ttu-id="2f0ca-115">Mit Antwort Aktionen können Sie häufige sicherheitsbezogene Aufgaben ausführen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-115">Response actions allow you to perform common security-related tasks.</span></span>

## <a name="sidebar"></a><span data-ttu-id="2f0ca-116">Randleiste</span><span class="sxs-lookup"><span data-stu-id="2f0ca-116">Sidebar</span></span>

<span data-ttu-id="2f0ca-117">Neben dem Hauptinhaltsbereich der Geräteprofil Seite befindet sich die Sidebar.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-117">Beside the main content area of the device profile page is the sidebar.</span></span>

![Registerkarte "Bild der Sidebar" für Geräteprofil](../../media/mtp-device-profile/azure-atp-only-device-sidebar.png)

<span data-ttu-id="2f0ca-119">In der Sidebar werden der vollständige Name und die Expositions Ebene des Geräts aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-119">The sidebar lists the device's full name and exposure level.</span></span> <span data-ttu-id="2f0ca-120">Sie enthält auch einige wichtige grundlegende Informationen in kleinen Unterabschnitten, die geöffnet oder geschlossen umgeschaltet werden können, beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="2f0ca-120">It also provides some important basic information in small subsections which can be toggled open or closed, such as:</span></span>

* <span data-ttu-id="2f0ca-121">**Tags** – alle Microsoft Defender ATP-, Azure ATP-oder Custom-Tags, die dem Gerät zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-121">**Tags** - Any Microsoft Defender ATP, Azure ATP, or custom tags associated with the device.</span></span> <span data-ttu-id="2f0ca-122">Tags aus Azure ATP können nicht bearbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-122">Tags from Azure ATP are not editable.</span></span>
* <span data-ttu-id="2f0ca-123">**Sicherheitsinformationen** – offene Vorfälle und aktive Warnungen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-123">**Security info** - Open incidents and active alerts.</span></span> <span data-ttu-id="2f0ca-124">Geräte, die in Microsoft Defender ATP registriert sind, zeigen außerdem die Expositions Ebene und das Risikoniveau an.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-124">Devices enrolled in Microsoft Defender ATP will also display exposure level and risk level.</span></span>

> [!TIP]
> <span data-ttu-id="2f0ca-125">Die Expositions Ebene bezieht sich darauf, wie viel das Gerät Sicherheitsempfehlungen einhält, während das Risikoniveau basierend auf einer Reihe von Faktoren berechnet wird, einschließlich der Typen und des Schweregrads aktiver Warnungen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-125">Exposure level relates to how much the device is complying with security recommendations, while risk level is calculated based on a number of factors, including the types and severity of active alerts.</span></span>

* <span data-ttu-id="2f0ca-126">**Gerätedetails** – Domäne, Betriebssystem, Zeitstempel für das erste erkennen des Geräts, IP-Adressen, Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-126">**Device details** - Domain, OS, timestamp for when the device was first seen, IP addresses, resources.</span></span> <span data-ttu-id="2f0ca-127">Für Geräte, die in Microsoft Defender ATP registriert sind, wird auch der Integritätsstatus angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-127">Devices enrolled in Microsoft Defender ATP also display health state.</span></span> <span data-ttu-id="2f0ca-128">In Azure ATP eingeschriebene Geräte zeigen Sam-Namen und einen Zeitstempel für den Zeitpunkt an, zu dem das Gerät erstmalig erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-128">Devices enrolled in Azure ATP will display SAM name and a timestamp for when the device was first created.</span></span>
* <span data-ttu-id="2f0ca-129">**Netzwerkaktivität** – Zeitstempel zum ersten Mal und zum letzten Mal, als das Gerät im Netzwerk angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-129">**Network activity** - Timestamps for the first time and last time the device was seen on the network.</span></span>
* <span data-ttu-id="2f0ca-130">**Verzeichnisdaten** (*nur für Geräte, die in Azure ATP registriert*sind) – [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) -Flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names)und Gruppenmitgliedschaften.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-130">**Directory data** (*only for devices enrolled in Azure ATP*) - [UAC](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/user-account-control-overview) flags, [SPNs](https://docs.microsoft.com/windows/win32/ad/service-principal-names), and group memberships.</span></span>

## <a name="response-actions"></a><span data-ttu-id="2f0ca-131">Antwort Aktionen</span><span class="sxs-lookup"><span data-stu-id="2f0ca-131">Response actions</span></span>

<span data-ttu-id="2f0ca-132">Reaktions Aktionen bieten eine schnelle Möglichkeit, Bedrohungen zu schützen und zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-132">Response actions offer a quick way to defend against and analyze threats.</span></span>

![Bild der Aktionsleiste für Geräteprofil](../../media/mtp-device-profile/hybrid-device-long-action-bar.png)

> [!IMPORTANT]
> * <span data-ttu-id="2f0ca-134">[Antwort Aktionen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) sind nur verfügbar, wenn das Gerät in Microsoft Defender ATP registriert ist.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-134">[Response actions](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts) are only available if the device is enrolled in Microsoft Defender ATP.</span></span>
> * <span data-ttu-id="2f0ca-135">Geräte, die in Microsoft Defender ATP registriert sind, können basierend auf dem Betriebssystem und der Versionsnummer des Geräts unterschiedliche Nummern von Antwort Aktionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-135">Devices that are enrolled in Microsoft Defender ATP may display different numbers of response actions, based on the device's OS and version number.</span></span>

<span data-ttu-id="2f0ca-136">Die auf der Geräteprofil Seite verfügbaren Aktionen umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2f0ca-136">Actions available on the device profile page include:</span></span>

* <span data-ttu-id="2f0ca-137">**Tags verwalten** – aktualisiert benutzerdefinierte Tags, die Sie auf dieses Gerät angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-137">**Manage tags** - Updates custom tags you have applied to this device.</span></span>
* <span data-ttu-id="2f0ca-138">**Gerät isolieren** – isoliert das Gerät aus dem Netzwerk Ihrer Organisation, während es mit dem Advanced Threat Protection von Microsoft Defender verbunden bleibt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-138">**Isolate device** - Isolates the device from your organization's network while keeping it connected to Microsoft Defender Advanced Threat Protection.</span></span> <span data-ttu-id="2f0ca-139">Sie können festlegen, dass Outlook, Teams und Skype for Business während der Isolierung des Geräts zu Kommunikationszwecken ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-139">You can choose to allow Outlook, Teams, and Skype for Business to run while the device is isolated, for communication purposes.</span></span>
* <span data-ttu-id="2f0ca-140">**Action Center** – zeigt den Status der übermittelten Aktionen an.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-140">**Action center** - View the status of submitted actions.</span></span> <span data-ttu-id="2f0ca-141">Nur verfügbar, wenn bereits eine andere Aktion ausgewählt wurde.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-141">Only available if another action has already been selected.</span></span>
* <span data-ttu-id="2f0ca-142">**Einschränken der APP-Ausführung** – verhindert, dass von Microsoft nicht signierte Anwendungen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-142">**Restrict app execution** - Prevents applications that are not signed by Microsoft from running.</span></span>
* <span data-ttu-id="2f0ca-143">**Antivirus-Scan ausführen** – aktualisiert die Antivirus-Definitionen von Windows Defender und führt sofort eine Antivirus-Überprüfung aus.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-143">**Run antivirus scan** - Updates Windows Defender Antivirus definitions and immediately runs an antivirus scan.</span></span> <span data-ttu-id="2f0ca-144">Wählen Sie zwischen Schnellscan oder vollständiger Scan aus.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-144">Choose between Quick scan or Full scan.</span></span>
* <span data-ttu-id="2f0ca-145">**Ermittlungs Paket sammeln** – sammelt Informationen zum Gerät.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-145">**Collect investigation package** - Gathers information about the device.</span></span> <span data-ttu-id="2f0ca-146">Wenn die Untersuchung abgeschlossen ist, können Sie Sie herunterladen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-146">When the investigation is completed, you can download it.</span></span>
* <span data-ttu-id="2f0ca-147">**Live-Antwort-Sitzung initiieren** – lädt eine Remote-Shell auf dem Gerät für [eingehende Sicherheitsuntersuchungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span><span class="sxs-lookup"><span data-stu-id="2f0ca-147">**Initiate Live Response Session** - Loads a remote shell on the device for [in-depth security investigations](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response).</span></span>
* <span data-ttu-id="2f0ca-148">**Initiieren der automatischen Untersuchung** – Automatisches [untersuchen und Beheben von Bedrohungen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span><span class="sxs-lookup"><span data-stu-id="2f0ca-148">**Initiate automated investigation** - Automatically [investigates and remediates threats](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air).</span></span> <span data-ttu-id="2f0ca-149">Sie können zwar manuell automatisierte Untersuchungen auslösen, die von dieser Seite ausgeführt werden, aber [bestimmte Warnungsrichtlinien](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) lösen selbst automatische Untersuchungen aus.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-149">Although you can manually trigger automated investigations to run from this page, [certain alert policies](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?view=o365-worldwide#default-alert-policies) trigger automatic investigations on their own.</span></span>
* <span data-ttu-id="2f0ca-150">**Action Center** – zeigt Informationen zu allen derzeit ausgeführten Reaktions Aktionen an.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-150">**Action center** - Displays information about any response actions that are currently running.</span></span>

## <a name="tabs-section"></a><span data-ttu-id="2f0ca-151">Tabs section</span><span class="sxs-lookup"><span data-stu-id="2f0ca-151">Tabs section</span></span>

<span data-ttu-id="2f0ca-152">Auf den Registerkarten für Geräteprofile können Sie eine Übersicht über Sicherheitsdetails zu dem Gerät und Tabellen mit einer Liste von Warnungen wechseln.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-152">The device profile tabs allow you to toggle through an overview of security details about the device, and tables containing a list of alerts.</span></span>

<span data-ttu-id="2f0ca-153">Für Geräte, die in Microsoft Defender ATP registriert sind, werden auch Registerkarten mit einer Zeitachse, eine Liste mit Sicherheitsempfehlungen, eine Softwareinventur, eine Liste der ermittelten Sicherheitsanfälligkeiten und fehlende KBS (Sicherheitsupdates) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-153">Devices enrolled in Microsoft Defender ATP will also display tabs that feature a timeline, a list of security recommendations, a software inventory, a list of discovered vulnerabilities, and missing KBs (security updates).</span></span>

### <a name="overview-tab"></a><span data-ttu-id="2f0ca-154">Registerkarte "Übersicht"</span><span class="sxs-lookup"><span data-stu-id="2f0ca-154">Overview tab</span></span>

<span data-ttu-id="2f0ca-155">Die Standardregisterkarte ist **Overview**.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-155">The default tab is **Overview**.</span></span> <span data-ttu-id="2f0ca-156">Es bietet einen schnellen Überblick über die wichtigsten Sicherheitsfakten zum Gerät.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-156">It provides a quick look at the most important security fact about the device.</span></span>

![Registerkarte ' Bild der Übersicht ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-overview.png)

<span data-ttu-id="2f0ca-158">Hier erhalten Sie einen kurzen Überblick über die aktiven Warnungen des Geräts sowie alle derzeit angemeldeten Benutzer.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-158">Here, you can get a quick look at the device's active alerts, and any currently logged on users.</span></span>

<span data-ttu-id="2f0ca-159">Wenn das Gerät in Microsoft Defender ATP registriert ist, sehen Sie auch die Risikostufe des Geräts sowie alle verfügbaren Daten zu Sicherheitsbewertungen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-159">If the device is enrolled in Microsoft Defender ATP, you will also see the device's risk level and any available data on security assessments.</span></span> <span data-ttu-id="2f0ca-160">In den Sicherheitsbewertungen wird die Expositions Stufe des Geräts beschrieben, Sicherheitsempfehlungen bereitgestellt und die betroffene Software sowie entdeckte Sicherheitsrisiken aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-160">The security assessments describe the device's exposure level, provide security recommendations, and list affected software and discovered vulnerabilities.</span></span>

### <a name="alerts-tab"></a><span data-ttu-id="2f0ca-161">Registerkarte "Warnungen"</span><span class="sxs-lookup"><span data-stu-id="2f0ca-161">Alerts tab</span></span>

<span data-ttu-id="2f0ca-162">Die Registerkarte **Benachrichtigungen** enthält eine Liste der Warnungen, die auf dem Gerät ausgelöst wurden, sowohl von Azure ATP als auch von Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-162">The **Alerts** tab contains a list of alerts that have been raised on the device, from both Azure ATP and Microsoft Defender ATP.</span></span>

![Registerkarte ' Bild der Benachrichtigungen ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-alerts.png)

<span data-ttu-id="2f0ca-164">Sie können die Anzahl der angezeigten Elemente sowie die für jedes Element angezeigten Spalten anpassen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-164">You can customize the number of items displayed, as well as which columns are displayed for each item.</span></span> <span data-ttu-id="2f0ca-165">Das Standardverhalten besteht darin, 30 Elemente pro Seite aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-165">The default behavior is to list thirty items per page.</span></span>

<span data-ttu-id="2f0ca-166">Die Spalten auf dieser Registerkarte enthalten Informationen über den Schweregrad der Bedrohung, die die Warnung ausgelöst hat, sowie den Status, den Untersuchungs Zustand und die Person, der die Warnung zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-166">The columns in this tab include information on the severity of the threat that triggered the alert, as well as status, investigation state, and who the alert has been assigned to.</span></span>

<span data-ttu-id="2f0ca-167">Die Spalte betroffene *Entitäten* bezieht sich auf das Gerät (Entität), dessen Profil Sie derzeit anzeigen, sowie alle anderen Geräte in Ihrem Netzwerk, die betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-167">The *impacted entities* column refers to the device (entity) whose profile you are currently viewing, plus any other devices in your network that are affected.</span></span>

<span data-ttu-id="2f0ca-168">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem noch weitere Informationen zur ausgewählten Warnung angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-168">Selecting an item from this list will open a flyout containing even more information about the selected alert.</span></span>

<span data-ttu-id="2f0ca-169">Diese Liste kann nach Schweregrad, Status oder der Person, der die Benachrichtigung zugewiesen wurde, gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-169">This list can be filtered by severity, status, or who the alert has been assigned to.</span></span>

### <a name="timeline-tab"></a><span data-ttu-id="2f0ca-170">Registerkarte "Timeline"</span><span class="sxs-lookup"><span data-stu-id="2f0ca-170">Timeline tab</span></span>

<span data-ttu-id="2f0ca-171">Die Registerkarte **Zeitachse** enthält ein interaktives, Chronologisches Diagramm aller Ereignisse, die auf dem Gerät ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-171">The **Timeline** tab includes an interactive, chronological chart of all events raised on the device.</span></span> <span data-ttu-id="2f0ca-172">Wenn Sie den markierten Bereich des Diagramms nach links oder rechts verschieben, können Sie Ereignisse über verschiedene Zeiträume hinweg anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-172">By moving the highlighted area of the chart left or right, you can view events over different periods of time.</span></span> <span data-ttu-id="2f0ca-173">Sie können auch einen benutzerdefinierten Datumsbereich aus dem Dropdownmenü zwischen dem interaktiven Diagramm und der Liste der Ereignisse auswählen.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-173">You can also choose a custom range of dates from the dropdown menu in between the interactive chart and the list of events.</span></span>

<span data-ttu-id="2f0ca-174">Unter dem Diagramm finden Sie eine Liste der Ereignisse für den ausgewählten Datumsbereich.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-174">Below the chart is a list of events for the selected range of dates.</span></span>

![Registerkarte ' Bild der Zeitachse ' für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-timeline.png)

<span data-ttu-id="2f0ca-176">Die Anzahl der angezeigten Elemente und die Spalten in der Liste können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-176">The number of items displayed and the columns on the list can both be customized.</span></span> <span data-ttu-id="2f0ca-177">In den Standardspalten werden die Ereigniszeit, der aktive Benutzer, der Aktionstyp, Entitäten (Prozesse) und zusätzliche Informationen zum Ereignis aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-177">The default columns list the event time, active user, action type, entities (processes), and additional information about the event.</span></span>

<span data-ttu-id="2f0ca-178">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem ein Ereignis Entitäten Diagramm mit den übergeordneten und untergeordneten Prozessen angezeigt wird, die an dem Ereignis beteiligt sind.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-178">Selecting an item from this list will open a flyout displaying an Event entities graph, showing the parent and child processes involved in the event.</span></span>

<span data-ttu-id="2f0ca-179">Die Liste kann nach der spezifischen Art des Ereignisses gefiltert werden; beispielsweise Registrierungs Ereignisse oder Smart Screen-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-179">The list can be filtered by the specific kind of event; for example, Registry events or Smart Screen Events.</span></span>

<span data-ttu-id="2f0ca-180">Die Liste kann auch als Download in eine CSV-Datei exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-180">The list can also be exported to a CSV file, for download.</span></span> <span data-ttu-id="2f0ca-181">Obwohl die Datei nicht durch die Anzahl der Ereignisse limitiert ist, beträgt der maximale Zeitbereich, den Sie exportieren können, sieben Tage.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-181">Although the file is not limited by number of events, the maximum time range you can choose to export is seven days.</span></span>

### <a name="security-recommendations-tab"></a><span data-ttu-id="2f0ca-182">Registerkarte "Sicherheitsempfehlungen"</span><span class="sxs-lookup"><span data-stu-id="2f0ca-182">Security recommendations tab</span></span>

<span data-ttu-id="2f0ca-183">Auf der Registerkarte **Sicherheitsempfehlungen** werden Aktionen aufgeführt, die Sie zum Schutz des Geräts ausführen können.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-183">The **Security recommendations** tab lists actions you can take to protect the device.</span></span> <span data-ttu-id="2f0ca-184">Wenn Sie ein Element in dieser Liste auswählen, wird ein Flyout geöffnet, in dem Sie Anweisungen dazu erhalten, wie Sie die Empfehlung anwenden können.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-184">Selecting an item on this list will open a flyout where you can get instructions on how to apply the recommendation.</span></span>

![Registerkarte Bild der Sicherheitsempfehlungen für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-security-recs.png)

<span data-ttu-id="2f0ca-186">Wie bei den vorherigen Registerkarten kann auch die Anzahl der Elemente, die pro Seite angezeigt werden, sowie die sichtbaren Spalten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-186">As with the previous tabs, the number of items displayed per page, as well as which columns are visible, can be customized.</span></span>

<span data-ttu-id="2f0ca-187">Die Standardansicht enthält Spalten, in denen die Sicherheitsschwächen, die zugehörige Bedrohung, die zugehörige Komponente oder Software, die von der Bedrohung betroffen ist, detailliert beschrieben werden und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-187">The default view includes columns that detail the security weaknesses addressed, the associated threat, the related component or software affected by the threat, and more.</span></span> <span data-ttu-id="2f0ca-188">Elemente können nach dem Status der Empfehlung gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-188">Items can be filtered by the recommendation's status.</span></span>

### <a name="software-inventory"></a><span data-ttu-id="2f0ca-189">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="2f0ca-189">Software inventory</span></span>

<span data-ttu-id="2f0ca-190">Auf der Registerkarte **Softwareinventur** sind auf dem Gerät installierte Software aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-190">The **Software inventory** tab lists software installed on the device.</span></span>

![Abbildung der Registerkarte "Softwareinventur" für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-software-inventory.png)

<span data-ttu-id="2f0ca-192">In der Standardansicht werden der Softwarehersteller, die installierte Versionsnummer, die Anzahl bekannter Software Schwächen, Einblicke in Bedrohungen, Produktcode und Tags angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-192">The default view displays the software vendor, installed version number, number of known software weaknesses, threat insights, product code, and tags.</span></span> <span data-ttu-id="2f0ca-193">Die Anzahl der angezeigten Elemente und die angezeigten Spalten können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-193">The number of items displayed and which columns are displayed can both be customized.</span></span>

<span data-ttu-id="2f0ca-194">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout mit weiteren Details zur ausgewählten Software sowie der Pfad und der Zeitstempel zum letzten Mal geöffnet, an dem die Software gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-194">Selecting an item from this list opens a flyout containing more details about the selected software, as well as the path and timestamp for the last time the software was found.</span></span>

<span data-ttu-id="2f0ca-195">Diese Liste kann nach Produktcode gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-195">This list can be filtered by product code.</span></span>

### <a name="discovered-vulnerabilities-tab"></a><span data-ttu-id="2f0ca-196">Registerkarte "erkannte Sicherheitsanfälligkeiten"</span><span class="sxs-lookup"><span data-stu-id="2f0ca-196">Discovered vulnerabilities tab</span></span>

<span data-ttu-id="2f0ca-197">Auf der Registerkarte **erkannte Sicherheitsanfälligkeiten** werden alle gängigen Sicherheitsanfälligkeiten und Exploits (CVEs) aufgelistet, die sich auf das Gerät auswirken können.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-197">The **Discovered vulnerabilities** tab lists any Common Vulnerabilities and Exploits (CVEs) that may affect the device.</span></span>

![Registerkarte "Abbild der entdeckten Sicherheitsanfälligkeiten" für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-discovered-vulnerabilities.png)

<span data-ttu-id="2f0ca-199">In der Standardansicht werden der Schweregrad von CVE, das Common Vulnerability Score (CVS), die Software im Zusammenhang mit CVE, der Veröffentlichung von CVE, der Zeitpunkt der letzten Aktualisierung von CVE und mit dem CVE verbundene Bedrohungen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-199">The default view lists the severity of the CVE, the Common Vulnerability Score (CVS), the software related to the CVE, when the CVE was published, when the CVE was last updated, and threats associated with the CVE.</span></span>

<span data-ttu-id="2f0ca-200">Wie bei den vorherigen Registerkarten kann auch die Anzahl der angezeigten Elemente und der sichtbaren Spalten angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-200">As with the previous tabs, the number of items displayed and which columns are visible can be customized.</span></span>

<span data-ttu-id="2f0ca-201">Wenn Sie ein Element aus dieser Liste auswählen, wird ein Flyout geöffnet, in dem das CVE beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-201">Selecting an item from this list will open a flyout that describes the CVE.</span></span>

### <a name="missing-kbs"></a><span data-ttu-id="2f0ca-202">Fehlende KBS</span><span class="sxs-lookup"><span data-stu-id="2f0ca-202">Missing KBs</span></span>

<span data-ttu-id="2f0ca-203">Auf der Registerkarte " **fehlende KBS** " werden alle Microsoft-Updates aufgelistet, die noch nicht auf das Gerät angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-203">The **Missing KBs** tab lists any Microsoft Updates that have yet to be applied to the device.</span></span> <span data-ttu-id="2f0ca-204">Bei der fraglichen "KBS" handelt es sich um [Knowledge Base-Artikel](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) , in denen diese Updates beschrieben werden. Beispiel: [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span><span class="sxs-lookup"><span data-stu-id="2f0ca-204">The "KBs" in question are [Knowledge Base articles](https://support.microsoft.com/help/242450/how-to-query-the-microsoft-knowledge-base-by-using-keywords-and-query) which describe these updates; for example, [KB4551762](https://support.microsoft.com/help/4551762/windows-10-update-kb4551762).</span></span>

![Abbildung fehlender KBS-Registerkarten für Geräteprofil](../../media/mtp-device-profile/hybrid-device-tab-missing-kbs.PNG)

<span data-ttu-id="2f0ca-206">In der Standardansicht wird das Bulletin mit den Updates, der Betriebssystemversion, betroffenen Produkten, CVEs, der KB-Nummer und Tags aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-206">The default view lists the bulletin containing the updates, OS version, products affected, CVEs addressed, the KB number, and tags.</span></span>

<span data-ttu-id="2f0ca-207">Die Anzahl der Elemente, die pro Seite angezeigt werden, und die angezeigten Spalten können angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-207">The number of items displayed per page and which columns are displayed can be customized.</span></span>

<span data-ttu-id="2f0ca-208">Durch die Auswahl eines Elements wird ein Flyout geöffnet, das auf das Update verweist.</span><span class="sxs-lookup"><span data-stu-id="2f0ca-208">Selecting an item will open a flyout that links to the update.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2f0ca-209">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2f0ca-209">Related topics</span></span>

* [<span data-ttu-id="2f0ca-210">Übersicht über Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2f0ca-210">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
* [<span data-ttu-id="2f0ca-211">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2f0ca-211">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
* [<span data-ttu-id="2f0ca-212">Untersuchen von Entitäten auf Geräten mithilfe von Live-Antwort</span><span class="sxs-lookup"><span data-stu-id="2f0ca-212">Investigate entities on devices, using live response</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/live-response)
* [<span data-ttu-id="2f0ca-213">Automatische Untersuchung und Reaktion (Air) in Office 365</span><span class="sxs-lookup"><span data-stu-id="2f0ca-213">Automated investigation and response (AIR) in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)

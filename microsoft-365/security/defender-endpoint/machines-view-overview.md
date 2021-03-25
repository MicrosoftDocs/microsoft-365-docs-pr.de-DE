---
title: Anzeigen und Organisieren der Microsoft Defender ATP-Geräteliste
description: Erfahren Sie mehr über die verfügbaren Features, die Sie in der Liste Geräte verwenden können, z. B. Sortieren, Filtern und Exportieren der Liste, um Untersuchungen zu verbessern.
keywords: sort, filter, export, csv, device name, domain, last seen, internal IP, health state, active alerts, active malware detections, threat category, review alerts, network, connection, malware, type, password stealer, ransomware, exploit, threat, general malware, unwanted software
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9068983b5f61305b1f3da4d076e99e71974e8df4
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185671"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a><span data-ttu-id="4db50-104">Anzeigen und Organisieren der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="4db50-104">View and organize the Microsoft Defender for Endpoint Devices list</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4db50-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="4db50-105">**Applies to:**</span></span>
- [<span data-ttu-id="4db50-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="4db50-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4db50-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4db50-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="4db50-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="4db50-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4db50-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="4db50-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)


<span data-ttu-id="4db50-110">Die **Liste Geräte** enthält eine Liste der Geräte in Ihrem Netzwerk, auf denen Warnungen generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4db50-110">The **Devices list** shows a list of the devices in your network where alerts were generated.</span></span> <span data-ttu-id="4db50-111">Standardmäßig werden in der Warteschlange Geräte angezeigt, die in den letzten 30 Tagen angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="4db50-111">By default, the queue displays devices seen in the last 30 days.</span></span>  

<span data-ttu-id="4db50-112">Auf einen Blick werden Informationen wie Domäne, Risikostufe, Betriebssystemplattform und andere Details zur einfachen Identifizierung der am stärksten gefährdeten Geräte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4db50-112">At a glance you'll see information such as domain, risk level, OS platform, and other details for easy identification of devices most at risk.</span></span>

<span data-ttu-id="4db50-113">Es stehen mehrere Optionen zur Verfügung, um die Gerätelistenansicht anzupassen.</span><span class="sxs-lookup"><span data-stu-id="4db50-113">There are several options you can choose from to customize the devices list view.</span></span> <span data-ttu-id="4db50-114">Im oberen Navigationsbereich können Sie:</span><span class="sxs-lookup"><span data-stu-id="4db50-114">On the top navigation you can:</span></span>

- <span data-ttu-id="4db50-115">Hinzufügen oder Entfernen von Spalten</span><span class="sxs-lookup"><span data-stu-id="4db50-115">Add or remove columns</span></span>
- <span data-ttu-id="4db50-116">Exportieren der gesamten Liste im CSV-Format</span><span class="sxs-lookup"><span data-stu-id="4db50-116">Export the entire list in CSV format</span></span>
- <span data-ttu-id="4db50-117">Auswählen der Anzahl der Elemente, die pro Seite angezeigt werden soll</span><span class="sxs-lookup"><span data-stu-id="4db50-117">Select the number of items to show per page</span></span>
- <span data-ttu-id="4db50-118">Anwenden von Filtern</span><span class="sxs-lookup"><span data-stu-id="4db50-118">Apply filters</span></span>

<span data-ttu-id="4db50-119">Während des Onboardingprozesses wird die **Liste Geräte** schrittweise mit Geräten aufgefüllt, wenn sie beginnen, Sensordaten zu melden.</span><span class="sxs-lookup"><span data-stu-id="4db50-119">During the onboarding process, the **Devices list** is gradually populated with devices as they begin to report sensor data.</span></span> <span data-ttu-id="4db50-120">Verwenden Sie diese Ansicht, um Ihre integrierten Endpunkte zu verfolgen, während sie online sind, oder laden Sie die vollständige Endpunktliste als CSV-Datei für die Offlineanalyse herunter.</span><span class="sxs-lookup"><span data-stu-id="4db50-120">Use this view to track your onboarded endpoints as they come online, or download the complete endpoint list as a CSV file for offline analysis.</span></span>

>[!NOTE]
> <span data-ttu-id="4db50-121">Wenn Sie die Geräteliste exportieren, enthält sie jedes Gerät in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4db50-121">If you export the device list, it will contain every device in your organization.</span></span> <span data-ttu-id="4db50-122">Je nachdem, wie groß Ihre Organisation ist, kann es sehr viel Zeit zum Herunterladen dauern.</span><span class="sxs-lookup"><span data-stu-id="4db50-122">It might take a significant amount of time to download, depending on how large your organization is.</span></span> <span data-ttu-id="4db50-123">Beim Exportieren der Liste im CSV-Format werden die Daten ungefiltert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4db50-123">Exporting the list in CSV format displays the data in an unfiltered manner.</span></span> <span data-ttu-id="4db50-124">Die CSV-Datei enthält alle Geräte in der Organisation, unabhängig davon, ob die Filterung in der Ansicht selbst angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4db50-124">The CSV file will include all devices in the organization, regardless of any filtering applied in the view itself.</span></span>

![Abbildung der Geräteliste mit Liste der Geräte](images/device-list.png)

## <a name="sort-and-filter-the-device-list"></a><span data-ttu-id="4db50-126">Sortieren und Filtern der Geräteliste</span><span class="sxs-lookup"><span data-stu-id="4db50-126">Sort and filter the device list</span></span>

<span data-ttu-id="4db50-127">Sie können die folgenden Filter anwenden, um die Liste der Warnungen zu beschränken und eine fokussierte Ansicht zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="4db50-127">You can apply the following filters to limit the list of alerts and get a more focused view.</span></span>

### <a name="risk-level"></a><span data-ttu-id="4db50-128">Risikostufe</span><span class="sxs-lookup"><span data-stu-id="4db50-128">Risk level</span></span>

<span data-ttu-id="4db50-129">Die Risikostufe spiegelt die allgemeine Risikobewertung des Geräts basierend auf einer Kombination von Faktoren wider, einschließlich der Typen und des Schweregrads aktiver Warnungen auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="4db50-129">The risk level reflects the overall risk assessment of the device based on a combination of factors, including the types and severity of active alerts on the device.</span></span> <span data-ttu-id="4db50-130">Das Auflösen aktiver Warnungen, das Genehmigen von Korrekturaktivitäten und das Unterdrücken nachfolgender Warnungen können die Risikostufe senken.</span><span class="sxs-lookup"><span data-stu-id="4db50-130">Resolving active alerts, approving remediation activities, and suppressing subsequent alerts can lower the risk level.</span></span>

### <a name="exposure-level"></a><span data-ttu-id="4db50-131">Belichtungsstufe</span><span class="sxs-lookup"><span data-stu-id="4db50-131">Exposure level</span></span>

<span data-ttu-id="4db50-132">Die Belichtungsstufe spiegelt die aktuelle Belichtung des Geräts basierend auf den kumulativen Auswirkungen der ausstehenden Sicherheitsempfehlungen wider.</span><span class="sxs-lookup"><span data-stu-id="4db50-132">The exposure level reflects the current exposure of the device based on the cumulative impact of its pending security recommendations.</span></span> <span data-ttu-id="4db50-133">Die möglichen Ebenen sind niedrig, mittel und hoch.</span><span class="sxs-lookup"><span data-stu-id="4db50-133">The possible levels are low, medium, and high.</span></span> <span data-ttu-id="4db50-134">Niedrige Belichtung bedeutet, dass Ihre Geräte weniger anfällig für die Nutzung sind.</span><span class="sxs-lookup"><span data-stu-id="4db50-134">Low exposure means your devices are less vulnerable from exploitation.</span></span>

<span data-ttu-id="4db50-135">Wenn die Risikostufe "Keine Daten verfügbar" ausdingt, gibt es einige Gründe, warum dies der Fall sein kann:</span><span class="sxs-lookup"><span data-stu-id="4db50-135">If the exposure level says "No data available," there are a few reasons why this may be the case:</span></span>

- <span data-ttu-id="4db50-136">Gerät hat die Berichterstellung für mehr als 30 Tage beendet – in diesem Fall gilt es als inaktiv, und die Belichtung wird nicht berechnet.</span><span class="sxs-lookup"><span data-stu-id="4db50-136">Device stopped reporting for more than 30 days – in that case it is considered inactive, and the exposure isn't computed</span></span>
- <span data-ttu-id="4db50-137">Gerätebetriebssystem nicht unterstützt – siehe [Mindestanforderungen für Microsoft Defender for Endpoint](minimum-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="4db50-137">Device OS not supported - see [minimum requirements for Microsoft Defender for Endpoint](minimum-requirements.md)</span></span>
- <span data-ttu-id="4db50-138">Gerät mit veralteten Agents (sehr unwahrscheinlich)</span><span class="sxs-lookup"><span data-stu-id="4db50-138">Device with stale agent (very unlikely)</span></span>

### <a name="os-platform"></a><span data-ttu-id="4db50-139">Betriebssystemplattform</span><span class="sxs-lookup"><span data-stu-id="4db50-139">OS Platform</span></span>

<span data-ttu-id="4db50-140">Wählen Sie nur die Betriebssystemplattformen aus, die Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4db50-140">Select only the OS platforms you're interested in investigating.</span></span>

### <a name="health-state"></a><span data-ttu-id="4db50-141">Integritätsstatus</span><span class="sxs-lookup"><span data-stu-id="4db50-141">Health state</span></span>

<span data-ttu-id="4db50-142">Filtern sie nach den folgenden Geräteintehzustandszuständen:</span><span class="sxs-lookup"><span data-stu-id="4db50-142">Filter by the following device health states:</span></span>

- <span data-ttu-id="4db50-143">**Aktiv** – Geräte, die aktiv Sensordaten an den Dienst melden.</span><span class="sxs-lookup"><span data-stu-id="4db50-143">**Active** – Devices that are actively reporting sensor data to the service.</span></span>
- <span data-ttu-id="4db50-144">**Inaktiv** – Geräte, die das Senden von Signalen für mehr als 7 Tage vollständig beendet haben.</span><span class="sxs-lookup"><span data-stu-id="4db50-144">**Inactive** – Devices that have completely stopped sending signals for more than 7 days.</span></span>
- <span data-ttu-id="4db50-145">**Falsch konfiguriert –** Geräte, die die Kommunikation mit dem Dienst beeinträchtigt haben oder keine Sensordaten senden können.</span><span class="sxs-lookup"><span data-stu-id="4db50-145">**Misconfigured** – Devices that have impaired communications with service or are unable to send sensor data.</span></span> <span data-ttu-id="4db50-146">Falsch konfigurierte Geräte können weiter wie folgt klassifiziert werden:</span><span class="sxs-lookup"><span data-stu-id="4db50-146">Misconfigured devices can further be classified to:</span></span>
  - <span data-ttu-id="4db50-147">Keine Sensordaten</span><span class="sxs-lookup"><span data-stu-id="4db50-147">No sensor data</span></span>
  - <span data-ttu-id="4db50-148">Beeinträchtigte Kommunikation</span><span class="sxs-lookup"><span data-stu-id="4db50-148">Impaired communications</span></span>

  <span data-ttu-id="4db50-149">Weitere Informationen zum Beheben von Problemen auf falsch konfigurierten Geräten finden Sie unter [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span><span class="sxs-lookup"><span data-stu-id="4db50-149">For more information on how to address issues on misconfigured devices see, [Fix unhealthy sensors](fix-unhealthy-sensors.md).</span></span>

### <a name="antivirus-status"></a><span data-ttu-id="4db50-150">Antivirusstatus</span><span class="sxs-lookup"><span data-stu-id="4db50-150">Antivirus status</span></span>

<span data-ttu-id="4db50-151">Filtern Von Geräten nach Antivirusstatus.</span><span class="sxs-lookup"><span data-stu-id="4db50-151">Filter devices by antivirus status.</span></span> <span data-ttu-id="4db50-152">Gilt nur für aktive Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="4db50-152">Applies to active Windows 10 devices only.</span></span>

- <span data-ttu-id="4db50-153">**Deaktiviert** – & Schutz vor Bedrohungen ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4db50-153">**Disabled** - Virus & threat protection is turned off.</span></span>
- <span data-ttu-id="4db50-154">**Keine Berichterstellung** – Virenschutz & wird nicht berichtet.</span><span class="sxs-lookup"><span data-stu-id="4db50-154">**Not reporting** - Virus & threat protection is not reporting.</span></span>
- <span data-ttu-id="4db50-155">**Nicht aktualisiert** – Virenschutz & bedrohungsschutz ist nicht auf dem neuesten Stand.</span><span class="sxs-lookup"><span data-stu-id="4db50-155">**Not updated** - Virus & threat protection is not up to date.</span></span>

<span data-ttu-id="4db50-156">Weitere Informationen finden Sie unter [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span><span class="sxs-lookup"><span data-stu-id="4db50-156">For more information, see [View the Threat & Vulnerability Management dashboard](tvm-dashboard-insights.md).</span></span>

### <a name="threat-mitigation-status"></a><span data-ttu-id="4db50-157">Status der Bedrohungsminderung</span><span class="sxs-lookup"><span data-stu-id="4db50-157">Threat mitigation status</span></span>

<span data-ttu-id="4db50-158">Um Geräte anzuzeigen, die möglicherweise von einer bestimmten Bedrohung betroffen sind, wählen Sie die Bedrohung im Dropdownmenü aus, und wählen Sie dann aus, welcher Sicherheitsrisikoaspekt abgemildert werden muss.</span><span class="sxs-lookup"><span data-stu-id="4db50-158">To view devices that may be affected by a certain threat, select the threat from the dropdown menu, and then select what vulnerability aspect needs to be mitigated.</span></span>

<span data-ttu-id="4db50-159">Weitere Informationen zu bestimmten Bedrohungen finden Sie unter [Threat analytics](threat-analytics.md).</span><span class="sxs-lookup"><span data-stu-id="4db50-159">To learn more about certain threats, see [Threat analytics](threat-analytics.md).</span></span> <span data-ttu-id="4db50-160">Informationen zur Risikominderung finden Sie unter [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span><span class="sxs-lookup"><span data-stu-id="4db50-160">For mitigation information, see [Threat & Vulnerability Management](next-gen-threat-and-vuln-mgt.md).</span></span>

### <a name="windows-10-version"></a><span data-ttu-id="4db50-161">Windows 10-Version</span><span class="sxs-lookup"><span data-stu-id="4db50-161">Windows 10 version</span></span>

<span data-ttu-id="4db50-162">Wählen Sie nur die Windows 10-Versionen aus, die Sie untersuchen möchten.</span><span class="sxs-lookup"><span data-stu-id="4db50-162">Select only the Windows 10 versions you're interested in investigating.</span></span>

### <a name="tags--groups"></a><span data-ttu-id="4db50-163">Tags & Gruppen</span><span class="sxs-lookup"><span data-stu-id="4db50-163">Tags & Groups</span></span>

<span data-ttu-id="4db50-164">Filtern Sie die Liste basierend auf der Gruppierung und Kennzeichnung, die Sie einzelnen Geräten hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="4db50-164">Filter the list based on the grouping and tagging that you've added to individual devices.</span></span> <span data-ttu-id="4db50-165">Weitere [Informationen finden Sie unter Erstellen und Verwalten von Gerätetags](machine-tags.md) und Erstellen und Verwalten von [Gerätegruppen.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="4db50-165">See [Create and manage device tags](machine-tags.md) and [Create and manage device groups](machine-groups.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4db50-166">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="4db50-166">Related topics</span></span>

- [<span data-ttu-id="4db50-167">Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste</span><span class="sxs-lookup"><span data-stu-id="4db50-167">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)

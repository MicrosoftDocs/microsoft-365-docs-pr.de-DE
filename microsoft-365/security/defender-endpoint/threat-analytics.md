---
title: Nachverfolgen und Reagieren auf neue Bedrohungen mit Microsoft Defender ATP-Bedrohungsanalyse
ms.reviewer: ''
description: Erfahren Sie mehr über neue Bedrohungen und Angriffstechniken und deren Beenden. Bewerten Sie ihre Auswirkungen auf Ihre Organisation und bewerten Sie Die Ausfallsicherheit Ihrer Organisation.
keywords: Bedrohungsanalyse, Risikobewertung, Betriebssystemminderung, Mikrocodeminderung, Risikominderungsstatus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 853a862556825e714bb06e51839f9c026e0cc0e0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51501185"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="da015-105">Nachverfolgen und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen</span><span class="sxs-lookup"><span data-stu-id="da015-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da015-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="da015-106">**Applies to:**</span></span>
- [<span data-ttu-id="da015-107">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="da015-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="da015-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da015-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="da015-109">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="da015-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="da015-110">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="da015-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="da015-111">Da anspruchsvollere Gegner und neue Bedrohungen häufig und weit verbreitet entstehen, ist es wichtig, schnell in der Lage zu sein:</span><span class="sxs-lookup"><span data-stu-id="da015-111">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="da015-112">Bewerten der Auswirkungen neuer Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="da015-112">Assess the impact of new threats</span></span>
- <span data-ttu-id="da015-113">Überprüfen Der Ausfallsicherheit gegenüber oder der Gefährdung der Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="da015-113">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="da015-114">Identifizieren der Aktionen, die Sie zum Beenden oder Eindähen der Bedrohungen ergreifen können</span><span class="sxs-lookup"><span data-stu-id="da015-114">Identify the actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="da015-115">Die Bedrohungsanalyse ist eine Reihe von Berichten von Microsoft-Sicherheitsexperten, die die relevantesten Bedrohungen abdecken, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="da015-115">Threat analytics is a set of reports from expert Microsoft security researchers covering the most relevant threats, including:</span></span>

- <span data-ttu-id="da015-116">Aktive Bedrohungsakteure und ihre Kampagnen</span><span class="sxs-lookup"><span data-stu-id="da015-116">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="da015-117">Beliebte und neue Angriffstechniken</span><span class="sxs-lookup"><span data-stu-id="da015-117">Popular and new attack techniques</span></span>
- <span data-ttu-id="da015-118">Kritische Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="da015-118">Critical vulnerabilities</span></span>
- <span data-ttu-id="da015-119">Allgemeine Angriffsoberflächen</span><span class="sxs-lookup"><span data-stu-id="da015-119">Common attack surfaces</span></span>
- <span data-ttu-id="da015-120">Verbreitete Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="da015-120">Prevalent malware</span></span>

<span data-ttu-id="da015-121">Jeder Bericht enthält eine detaillierte Analyse einer Bedrohung und umfassende Anleitungen zum Schutz vor dieser Bedrohung.</span><span class="sxs-lookup"><span data-stu-id="da015-121">Each report provides a detailed analysis of a threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="da015-122">Es enthält auch Daten aus Ihrem Netzwerk, die angeben, ob die Bedrohung aktiv ist und ob Sie über entsprechende Schutzmaßnahmen verfügen.</span><span class="sxs-lookup"><span data-stu-id="da015-122">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

<span data-ttu-id="da015-123">Sehen Sie sich dieses kurze Video an, um mehr darüber zu erfahren, wie Sie mithilfe von Bedrohungsanalysen die neuesten Bedrohungen nachverfolgen und beenden können.</span><span class="sxs-lookup"><span data-stu-id="da015-123">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>
<p></p>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bw1f]

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="da015-124">Anzeigen des Dashboards für die Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="da015-124">View the threat analytics dashboard</span></span>

<span data-ttu-id="da015-125">Das Dashboard für die Bedrohungsanalyse ist ein hervorragender Ausgangspunkt, um zu den Berichten zu kommen, die für Ihre Organisation am relevantesten sind.</span><span class="sxs-lookup"><span data-stu-id="da015-125">The threat analytics dashboard is a great jump off point for getting to the reports that are most relevant to your organization.</span></span> <span data-ttu-id="da015-126">Es fasst die Bedrohungen in den folgenden Abschnitten zusammen:</span><span class="sxs-lookup"><span data-stu-id="da015-126">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="da015-127">**Neueste Bedrohungen**– listet die zuletzt veröffentlichten Bedrohungsberichte sowie die Anzahl der Geräte mit aktiven und aufgelösten Warnungen auf.</span><span class="sxs-lookup"><span data-stu-id="da015-127">**Latest threats**—lists the most recently published threat reports, along with the number of devices with active and resolved alerts.</span></span>
- <span data-ttu-id="da015-128">**Bedrohungen mit hoher** Auswirkung – listet die Bedrohungen auf, die die höchsten Auswirkungen auf die Organisation hatten.</span><span class="sxs-lookup"><span data-stu-id="da015-128">**High-impact threats**—lists the threats that have had the highest impact to the organization.</span></span> <span data-ttu-id="da015-129">In diesem Abschnitt werden Bedrohungen nach der Anzahl der Geräte mit aktiven Warnungen enteilt.</span><span class="sxs-lookup"><span data-stu-id="da015-129">This section ranks threats by the number of devices that have active alerts.</span></span>
- <span data-ttu-id="da015-130">**Bedrohungszusammenfassung**– zeigt die Gesamtwirkung von nachverfolgten Bedrohungen, indem die Anzahl der Bedrohungen mit aktiven und aufgelösten Warnungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="da015-130">**Threat summary**—shows the overall impact of tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="da015-131">Wählen Sie eine Bedrohung aus dem Dashboard aus, um den Bericht für diese Bedrohung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="da015-131">Select a threat from the dashboard to view the report for that threat.</span></span>

![Abbildung eines Dashboards für die Bedrohungsanalyse](images/ta_dashboard.png)

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="da015-133">Anzeigen eines Berichts zur Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="da015-133">View a threat analytics report</span></span>

<span data-ttu-id="da015-134">Jeder Bericht zur Bedrohungsanalyse enthält Informationen in drei Abschnitten: **Overview**, **Analyst report** und **Mitigations**.</span><span class="sxs-lookup"><span data-stu-id="da015-134">Each threat analytics report provides information in three sections: **Overview**, **Analyst report**, and **Mitigations**.</span></span>

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="da015-135">Übersicht: Schnelles Verständnis der Bedrohung, Bewerten der Auswirkungen und Überprüfen der Abwehr</span><span class="sxs-lookup"><span data-stu-id="da015-135">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="da015-136">Der **Abschnitt Übersicht** bietet eine Vorschau des detaillierten Analystenberichts.</span><span class="sxs-lookup"><span data-stu-id="da015-136">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="da015-137">Außerdem enthält sie Diagramme, die die Auswirkungen der Bedrohung für Ihre Organisation und Ihre Gefährdung durch falsch konfigurierte und nicht gepatchte Geräte hervorheben.</span><span class="sxs-lookup"><span data-stu-id="da015-137">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

<span data-ttu-id="da015-138">![Abbildung des Abschnitts "Übersicht" eines Berichts zur Bedrohungsanalyse ](images/ta-overview.png)
 _(Übersicht) eines Berichts zur Bedrohungsanalyse_</span><span class="sxs-lookup"><span data-stu-id="da015-138">![Image of the overview section of a threat analytics report](images/ta-overview.png)
_Overview section of a threat analytics report_</span></span>

#### <a name="assess-the-impact-to-your-organization"></a><span data-ttu-id="da015-139">Bewerten der Auswirkungen auf Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="da015-139">Assess the impact to your organization</span></span>
<span data-ttu-id="da015-140">Jeder Bericht enthält Diagramme, die Informationen zu den organisatorischen Auswirkungen einer Bedrohung liefern sollen:</span><span class="sxs-lookup"><span data-stu-id="da015-140">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>
- <span data-ttu-id="da015-141">**Geräte mit Warnungen**– zeigt die aktuelle Anzahl unterschiedlicher Geräte an, die von der Bedrohung betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="da015-141">**Devices with alerts**—shows the current number of distinct devices that have been impacted by the threat.</span></span> <span data-ttu-id="da015-142">Ein Gerät wird als **Aktiv** kategorisiert, wenn dieser Bedrohung mindestens  eine Warnung zugeordnet ist, und **Resolved,** wenn alle Warnungen im Zusammenhang mit der Bedrohung auf dem Gerät aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="da015-142">A device is categorized as **Active** if there is at least one alert associated with that threat and **Resolved** if *all* alerts associated with the threat on the device have been resolved.</span></span>
- <span data-ttu-id="da015-143">**Geräte mit Warnungen im** Laufe der Zeit – zeigt die Anzahl unterschiedlicher Geräte mit **aktiven** und **aufgelösten** Warnungen im Laufe der Zeit an.</span><span class="sxs-lookup"><span data-stu-id="da015-143">**Devices with alerts over time**—shows the number of distinct devices with **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="da015-144">Die Anzahl der aufgelösten Warnungen gibt an, wie schnell Ihre Organisation auf Warnungen reagiert, die einer Bedrohung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="da015-144">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="da015-145">Idealerweise sollte das Diagramm Warnungen anzeigen, die innerhalb weniger Tage aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="da015-145">Ideally, the chart should be showing alerts resolved within a few days.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="da015-146">Überprüfen der Ausfallsicherheit und -haltung</span><span class="sxs-lookup"><span data-stu-id="da015-146">Review security resilience and posture</span></span>
<span data-ttu-id="da015-147">Jeder Bericht enthält Diagramme, die einen Überblick darüber bieten, wie widerstandsfähig Ihre Organisation gegen eine bestimmte Bedrohung ist:</span><span class="sxs-lookup"><span data-stu-id="da015-147">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>
- <span data-ttu-id="da015-148">**Sicherheitskonfigurationsstatus**: Zeigt die Anzahl der Geräte an, die die empfohlenen Sicherheitseinstellungen angewendet haben, um die Bedrohung zu mindern.</span><span class="sxs-lookup"><span data-stu-id="da015-148">**Security configuration status**—shows the number of devices that have applied the recommended security settings that can help mitigate the threat.</span></span> <span data-ttu-id="da015-149">Geräte gelten als **sicher,** wenn sie _alle_ nachverfolgten Einstellungen angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="da015-149">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="da015-150">**Status des Sicherheitsrisikopatchings**– Zeigt die Anzahl der Geräte an, auf die Sicherheitsupdates oder Patches angewendet wurden, die Sicherheitsrisiken ausnutzen, die von der Bedrohung ausgenutzt wurden.</span><span class="sxs-lookup"><span data-stu-id="da015-150">**Vulnerability patching status**—shows the number of devices that have applied security updates or patches that address vulnerabilities exploited by the threat.</span></span>

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="da015-151">Analystenbericht: Experten-Einblick von Microsoft-Sicherheitsforschern erhalten</span><span class="sxs-lookup"><span data-stu-id="da015-151">Analyst report: Get expert insight from Microsoft security researchers</span></span>
<span data-ttu-id="da015-152">Wechseln Sie zum **Abschnitt Analyst report,** um die detaillierten Experten-Schreibzugriffe zu lesen.</span><span class="sxs-lookup"><span data-stu-id="da015-152">Go to the **Analyst report** section to read through the detailed expert write-up.</span></span> <span data-ttu-id="da015-153">Die meisten Berichte enthalten detaillierte Beschreibungen von Angriffsketten, einschließlich Taktiken und Techniken, die dem MITRE ATT&CK-Framework zugeordnet sind, umfassende Empfehlungen und leistungsstarke Anleitungen zur [Bedrohungssuche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="da015-153">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="da015-154">Weitere Informationen zum Analystenbericht</span><span class="sxs-lookup"><span data-stu-id="da015-154">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="da015-155">Gegenmaßnahmen: Überprüfen der Liste der Gegenmaßnahmen und des Status Ihrer Geräte</span><span class="sxs-lookup"><span data-stu-id="da015-155">Mitigations: Review list of mitigations and the status of your devices</span></span>
<span data-ttu-id="da015-156">Überprüfen Sie **im Abschnitt** Gegenmaßnahmen die Liste der spezifischen Empfehlungen für Aktionen, die Ihnen helfen können, Ihre Ausfallsicherheit gegenüber der Bedrohung zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="da015-156">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="da015-157">Die Liste der nachverfolgten Gegenmaßnahmen umfasst:</span><span class="sxs-lookup"><span data-stu-id="da015-157">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="da015-158">**Sicherheitsupdates**– Bereitstellung von Sicherheitsupdates oder Patches für Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="da015-158">**Security updates**—deployment of security updates or patches for vulnerabilities</span></span>
- <span data-ttu-id="da015-159">**Microsoft Defender Antivirus-Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="da015-159">**Microsoft Defender Antivirus settings**</span></span>
  - <span data-ttu-id="da015-160">Security Intelligence Version</span><span class="sxs-lookup"><span data-stu-id="da015-160">Security intelligence version</span></span>
  - <span data-ttu-id="da015-161">In der Cloud zugestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="da015-161">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="da015-162">Schutz potenziell unerwünschter Anwendungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="da015-162">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="da015-163">Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="da015-163">Real-time protection</span></span>
 
<span data-ttu-id="da015-164">Informationen zur Risikominderung in [](next-gen-threat-and-vuln-mgt.md)diesem Abschnitt enthalten Daten aus der Bedrohungs- und Sicherheitsrisikoverwaltung, die auch detaillierte Drilldowninformationen aus verschiedenen Links im Bericht enthält.</span><span class="sxs-lookup"><span data-stu-id="da015-164">Mitigation information in this section incorporates data from [threat and vulnerability management](next-gen-threat-and-vuln-mgt.md), which also provides detailed drill-down information from various links in the report.</span></span>

<span data-ttu-id="da015-165">![Abbildung des Abschnitts "Gegenmaßnahmen" eines Berichts "Risikoanalysemaßnahmen" eines ](images/ta-mitigations.png)
 _Berichts zur Bedrohungsanalyse_</span><span class="sxs-lookup"><span data-stu-id="da015-165">![Image of the mitigations section of a threat analytics report](images/ta-mitigations.png)
_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="da015-166">Zusätzliche Berichtsdetails und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="da015-166">Additional report details and limitations</span></span>
<span data-ttu-id="da015-167">Beachten Sie bei der Verwendung der Berichte Folgendes:</span><span class="sxs-lookup"><span data-stu-id="da015-167">When using the reports, keep the following in mind:</span></span> 

- <span data-ttu-id="da015-168">Die Daten werden basierend auf ihrem rollenbasierten Zugriffssteuerungsbereich (RBAC) bereichiert.</span><span class="sxs-lookup"><span data-stu-id="da015-168">Data is scoped based on your role-based access control (RBAC) scope.</span></span> <span data-ttu-id="da015-169">Sie sehen den Status von Geräten in [Gruppen, auf die Sie zugreifen können.](machine-groups.md)</span><span class="sxs-lookup"><span data-stu-id="da015-169">You will see the status of devices in [groups that you can access](machine-groups.md).</span></span>
- <span data-ttu-id="da015-170">Diagramme spiegeln nur nachverfolgte Gegenmaßnahmen wider.</span><span class="sxs-lookup"><span data-stu-id="da015-170">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="da015-171">Überprüfen Sie die Berichtsübersicht auf zusätzliche Gegenmaßnahmen, die nicht in den Diagrammen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="da015-171">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="da015-172">Gegenmaßnahmen garantieren keine vollständige Ausfallsicherheit.</span><span class="sxs-lookup"><span data-stu-id="da015-172">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="da015-173">Die bereitgestellten Gegenmaßnahmen spiegeln die bestmöglichen Maßnahmen wider, die zur Verbesserung der Ausfallsicherheit erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="da015-173">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="da015-174">Geräte werden als "nicht verfügbar" gezählt, wenn sie keine Daten an den Dienst übermittelt haben.</span><span class="sxs-lookup"><span data-stu-id="da015-174">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="da015-175">Antivirusbezogene Statistiken basieren auf Microsoft Defender Antivirus-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="da015-175">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="da015-176">Geräte mit Antivirenlösungen von Drittanbietern können als "verfügbar" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="da015-176">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="da015-177">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="da015-177">Related topics</span></span>
- [<span data-ttu-id="da015-178">Proaktives Aufsuchen von Bedrohungen mit erweiterter Suche</span><span class="sxs-lookup"><span data-stu-id="da015-178">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="da015-179">Verstehen des Abschnitts "Analystenbericht"</span><span class="sxs-lookup"><span data-stu-id="da015-179">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="da015-180">Bewerten und Beheben von Sicherheitsschwächen und -risiken</span><span class="sxs-lookup"><span data-stu-id="da015-180">Assess and resolve security weaknesses and exposures</span></span>](next-gen-threat-and-vuln-mgt.md)
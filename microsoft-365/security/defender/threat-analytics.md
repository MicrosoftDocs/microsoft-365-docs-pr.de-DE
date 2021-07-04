---
title: Nachverfolgen von und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen
ms.reviewer: ''
description: Erfahren Sie mehr über neue Bedrohungen und Angriffstechniken und wie Sie sie stoppen können. Bewerten Sie deren Auswirkungen auf Ihre Organisation und bewerten Sie die Resilienz Ihrer Organisation.
keywords: Bedrohungsanalyse, Risikobewertung, Microsoft 365 Defender, M365D, Risikominderungsstatus, sichere Konfiguration, Microsoft Defender für Office 365, Microsoft Defender für Office 365 Bedrohungsanalyse, MDO-Bedrohungsanalyse, integrierte MDE- und MDO-Bedrohungsanalysedaten, Integration von Bedrohungsanalysedaten, integrierte Microsoft 365 Defender Bedrohungsanalyse
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c03dfef28744e2ee565c25d921902b8d11ecb7a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290243"
---
# <a name="track-and-respond-to-emerging-threats-with-threat-analytics"></a><span data-ttu-id="9f133-105">Nachverfolgen von und Reagieren auf neue Bedrohungen mit Bedrohungsanalysen</span><span class="sxs-lookup"><span data-stu-id="9f133-105">Track and respond to emerging threats with threat analytics</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9f133-106">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9f133-106">**Applies to:**</span></span>
- <span data-ttu-id="9f133-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9f133-107">Microsoft 365 Defender</span></span>

> <span data-ttu-id="9f133-108">Sie möchten Microsoft 365 Defender ausprobieren?</span><span class="sxs-lookup"><span data-stu-id="9f133-108">Want to experience Microsoft 365 Defender?</span></span> <span data-ttu-id="9f133-109">Sie können [in einer Laborumgebung auswerten](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) oder [ein Pilotprojekt in der Produktionsumgebung ausführen](m365d-pilot.md?ocid=cx-evalpilot).</span><span class="sxs-lookup"><span data-stu-id="9f133-109">You can [evaluate it in a lab environment](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) or [run your pilot project in production](m365d-pilot.md?ocid=cx-evalpilot).</span></span>
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="9f133-110">Die Bedrohungsanalyse ist unsere produktinterne Threat Intelligence-Lösung von erfahrenen Microsoft-Sicherheitsexperten, die Sicherheitsteams dabei unterstützt, so effizient wie möglich zu sein, während sie sich neuen Bedrohungen gegenübersehen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="9f133-110">Threat analytics is our in-product threat intelligence solution from expert Microsoft security researchers, designed to assist security teams to be as efficient as possible while facing emerging threats, including:</span></span>

- <span data-ttu-id="9f133-111">Aktive Bedrohungsteilnehmer und ihre Kampagnen</span><span class="sxs-lookup"><span data-stu-id="9f133-111">Active threat actors and their campaigns</span></span>
- <span data-ttu-id="9f133-112">Beliebte und neue Angriffstechniken</span><span class="sxs-lookup"><span data-stu-id="9f133-112">Popular and new attack techniques</span></span>
- <span data-ttu-id="9f133-113">Kritische Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="9f133-113">Critical vulnerabilities</span></span>
- <span data-ttu-id="9f133-114">Häufige Angriffsflächen</span><span class="sxs-lookup"><span data-stu-id="9f133-114">Common attack surfaces</span></span>
- <span data-ttu-id="9f133-115">Weit verbreitete Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="9f133-115">Prevalent malware</span></span>

<span data-ttu-id="9f133-116">Sehen Sie sich dieses kurze Video an, um mehr darüber zu erfahren, wie Bedrohungsanalysen Ihnen helfen können, die neuesten Bedrohungen nachzuverfolgen und zu beenden.</span><span class="sxs-lookup"><span data-stu-id="9f133-116">Watch this short video to learn more about how threat analytics can help you track the latest threats and stop them.</span></span>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWwJfU]

<span data-ttu-id="9f133-117">Sie können auf die Bedrohungsanalyse entweder über die obere linke Seite der Navigationsleiste Microsoft 365 Sicherheitsportals oder über eine dedizierte Dashboardkarte zugreifen, die die wichtigsten Bedrohungen in Ihrer Organisation anzeigt. Wenn Sie Einblicke in aktive oder laufende Kampagnen erhalten und wissen, was mithilfe von Bedrohungsanalysen zu tun ist, können Sie Ihr Sicherheitsteam mit fundierten Entscheidungen ausstatten.</span><span class="sxs-lookup"><span data-stu-id="9f133-117">You can access threat analytics either from the upper left-hand side of Microsoft 365 security portal’s navigation bar, or from a dedicated dashboard card which shows the top threats in your org. Getting visibility on active or ongoing campaigns and knowing what to do through threat analytics can help equip your security operations team with informed decisions.</span></span> 

![Abbildung des Dashboards für die Bedrohungsanalyse](../../media/threat-analytics/ta_inlandingpage_mtp.png)

<span data-ttu-id="9f133-119">_Zugriff auf Bedrohungsanalysen_</span><span class="sxs-lookup"><span data-stu-id="9f133-119">_Where to access threat analytics_</span></span>

<span data-ttu-id="9f133-120">Mit komplexeren Angreifern und neuen Bedrohungen, die häufig und weit verbreitet auftreten, ist es wichtig, schnell zu sein:</span><span class="sxs-lookup"><span data-stu-id="9f133-120">With more sophisticated adversaries and new threats emerging frequently and prevalently, it's critical to be able to quickly:</span></span>

- <span data-ttu-id="9f133-121">Erkennen und Reagieren auf neue Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="9f133-121">Identify and react to emerging threats</span></span>
- <span data-ttu-id="9f133-122">Erfahren Sie, ob Sie derzeit angegriffen werden</span><span class="sxs-lookup"><span data-stu-id="9f133-122">Learn if you are currently under attack</span></span>
- <span data-ttu-id="9f133-123">Bewerten der Auswirkungen der Bedrohung auf Ihre Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9f133-123">Assess the impact of the threat to your assets</span></span>
- <span data-ttu-id="9f133-124">Überprüfen Sie Ihre Resilienz gegenüber bedrohungen oder deren Gefährdung</span><span class="sxs-lookup"><span data-stu-id="9f133-124">Review your resilience against or exposure to the threats</span></span>
- <span data-ttu-id="9f133-125">Identifizieren Sie die Maßnahmen zur Risikominderung, Wiederherstellung oder Verhinderung, die Sie ergreifen können, um die Bedrohungen zu beenden oder einzudämmen.</span><span class="sxs-lookup"><span data-stu-id="9f133-125">Identify the mitigation, recovery, or prevention actions you can take to stop or contain the threats</span></span>

<span data-ttu-id="9f133-126">Jeder Bericht enthält eine Analyse einer nachverfolgten Bedrohung und umfassende Anleitungen zum Schutz vor dieser Bedrohung.</span><span class="sxs-lookup"><span data-stu-id="9f133-126">Each report provides an analysis of a tracked threat and extensive guidance on how to defend against that threat.</span></span> <span data-ttu-id="9f133-127">Es enthält auch Daten aus Ihrem Netzwerk, die angeben, ob die Bedrohung aktiv ist und ob Sie über entsprechende Schutzmaßnahmen verfügen.</span><span class="sxs-lookup"><span data-stu-id="9f133-127">It also incorporates data from your network, indicating whether the threat is active and if you have applicable protections in place.</span></span>

## <a name="view-the-threat-analytics-dashboard"></a><span data-ttu-id="9f133-128">Anzeigen des Dashboards für die Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="9f133-128">View the threat analytics dashboard</span></span>

<span data-ttu-id="9f133-129">Im Dashboard für die Bedrohungsanalyse ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) werden die Berichte hervorgehoben, die für Ihre Organisation am relevantesten sind.</span><span class="sxs-lookup"><span data-stu-id="9f133-129">The threat analytics dashboard ([security.microsoft.com/threatanalytics3](https://security.microsoft.com/threatanalytics3)) highlights the reports that are most relevant to your organization.</span></span> <span data-ttu-id="9f133-130">Sie fasst die Bedrohungen in den folgenden Abschnitten zusammen:</span><span class="sxs-lookup"><span data-stu-id="9f133-130">It summarizes the threats in the following sections:</span></span>

- <span data-ttu-id="9f133-131">**Aktuelle Bedrohungen**– listet die zuletzt veröffentlichten oder aktualisierten Bedrohungsberichte sowie die Anzahl der aktiven und aufgelösten Warnungen auf.</span><span class="sxs-lookup"><span data-stu-id="9f133-131">**Latest threats**—lists the most recently published or updated threat reports, along with the number of active and resolved alerts.</span></span>
- <span data-ttu-id="9f133-132">**Bedrohungen** mit hoher Auswirkung – listet die Bedrohungen auf, die die größten Auswirkungen auf Ihre Organisation haben.</span><span class="sxs-lookup"><span data-stu-id="9f133-132">**High-impact threats**—lists the threats that have the highest impact to your organization.</span></span> <span data-ttu-id="9f133-133">In diesem Abschnitt werden Bedrohungen mit der höchsten Anzahl aktiver und aufgelöster Warnungen zuerst aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f133-133">This section lists threats with the highest number of active and resolved alerts first.</span></span>
- <span data-ttu-id="9f133-134">**Bedrohungszusammenfassung**: Bietet die Gesamtauswirkung aller nachverfolgten Bedrohungen, indem die Anzahl der Bedrohungen mit aktiven und aufgelösten Warnungen angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9f133-134">**Threat summary**—provides the overall impact of all tracked threats by showing the number of threats with active and resolved alerts.</span></span>

<span data-ttu-id="9f133-135">Wählen Sie im Dashboard eine Bedrohung aus, um den Bericht für diese Bedrohung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f133-135">Select a threat from the dashboard to view the report for that threat.</span></span>

![Screenshot des Dashboards für die Bedrohungsanalyse](../../media/threat-analytics/ta_dashboard_mtp.png)

<span data-ttu-id="9f133-137">_Dashboard für die Bedrohungsanalyse. Sie können auch auf das Suchsymbol klicken, um einen Schlüssel in einem Schlüsselwort im Zusammenhang mit dem Bericht zur Bedrohungsanalyse zu erhalten, den Sie lesen möchten._</span><span class="sxs-lookup"><span data-stu-id="9f133-137">_Threat analytics dashboard. You can also click the Search icon to key in a keyword related to the threat analytics report that you'd like to read._</span></span> 

## <a name="view-a-threat-analytics-report"></a><span data-ttu-id="9f133-138">Anzeigen eines Berichts zur Bedrohungsanalyse</span><span class="sxs-lookup"><span data-stu-id="9f133-138">View a threat analytics report</span></span>

<span data-ttu-id="9f133-139">Jeder Bericht zur Bedrohungsanalyse enthält Informationen in mehreren Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="9f133-139">Each threat analytics report provides information in several sections:</span></span>

- [<span data-ttu-id="9f133-140">**Übersicht**</span><span class="sxs-lookup"><span data-stu-id="9f133-140">**Overview**</span></span>](#overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses)
- [<span data-ttu-id="9f133-141">**Analystenbericht**</span><span class="sxs-lookup"><span data-stu-id="9f133-141">**Analyst report**</span></span>](#analyst-report-get-expert-insight-from-microsoft-security-researchers)
- [<span data-ttu-id="9f133-142">**Verwandte Vorfälle**</span><span class="sxs-lookup"><span data-stu-id="9f133-142">**Related incidents**</span></span>](#related-incidents-view-and-manage-related-incidents)
- [<span data-ttu-id="9f133-143">**Betroffene Ressourcen**</span><span class="sxs-lookup"><span data-stu-id="9f133-143">**Impacted assets**</span></span>](#impacted-assets-get-list-of-impacted-devices-and-mailboxes)
- [<span data-ttu-id="9f133-144">**Verhinderte E-Mail-Versuche**</span><span class="sxs-lookup"><span data-stu-id="9f133-144">**Prevented email attempts**</span></span>](#prevented-email-attempts-view-blocked-or-junked-threat-emails)
- [<span data-ttu-id="9f133-145">**Risikominderungen**</span><span class="sxs-lookup"><span data-stu-id="9f133-145">**Mitigations**</span></span>](#mitigations-review-list-of-mitigations-and-the-status-of-your-devices)

### <a name="overview-quickly-understand-the-threat-assess-its-impact-and-review-defenses"></a><span data-ttu-id="9f133-146">Übersicht: Schnelles Verständnis der Bedrohung, Bewertung der Auswirkungen und Überprüfung von Schutzmaßnahmen</span><span class="sxs-lookup"><span data-stu-id="9f133-146">Overview: Quickly understand the threat, assess its impact, and review defenses</span></span>

<span data-ttu-id="9f133-147">Der Abschnitt **"Übersicht"** bietet eine Vorschau des detaillierten Analystenberichts.</span><span class="sxs-lookup"><span data-stu-id="9f133-147">The **Overview** section provides a preview of the detailed analyst report.</span></span> <span data-ttu-id="9f133-148">Außerdem werden Diagramme bereitgestellt, die die Auswirkungen der Bedrohung für Ihre Organisation und Ihre Gefährdung durch falsch konfigurierte und nicht gepatchte Geräte hervorheben.</span><span class="sxs-lookup"><span data-stu-id="9f133-148">It also provides charts that highlight the impact of the threat to your organization and your exposure through misconfigured and unpatched devices.</span></span>

![Abbildung des Übersichtsbereichs eines Berichts zur Bedrohungsanalyse](../../media/threat-analytics/ta_overview_mtp.png)

<span data-ttu-id="9f133-150">_Übersichtsabschnitt eines Berichts zur Bedrohungsanalyse_</span><span class="sxs-lookup"><span data-stu-id="9f133-150">_Overview section of a threat analytics report_</span></span>

#### <a name="assess-impact-on-your-organization"></a><span data-ttu-id="9f133-151">Bewerten der Auswirkungen auf Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="9f133-151">Assess impact on your organization</span></span>

<span data-ttu-id="9f133-152">Jeder Bericht enthält Diagramme, die Informationen über die Auswirkungen einer Bedrohung auf die Organisation bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="9f133-152">Each report includes charts designed to provide information about the organizational impact of a threat:</span></span>

- <span data-ttu-id="9f133-153">**Verwandte Vorfälle**– bietet eine Übersicht über die Auswirkungen der nachverfolgten Bedrohung für Ihre Organisation mit den folgenden Daten:</span><span class="sxs-lookup"><span data-stu-id="9f133-153">**Related incidents**—provides an overview of the impact of the tracked threat to your organization with the following data:</span></span>
  - <span data-ttu-id="9f133-154">Anzahl der aktiven Warnungen und anzahl der aktiven Vorfälle, denen sie zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="9f133-154">Number of active alerts and the number of active incidents they are associated with</span></span>
  - <span data-ttu-id="9f133-155">Schweregrad der aktiven Vorfälle</span><span class="sxs-lookup"><span data-stu-id="9f133-155">Severity of active incidents</span></span>
- <span data-ttu-id="9f133-156">**Warnungen im Laufe** der Zeit – zeigt die Anzahl der **zugehörigen aktiven** und **aufgelösten** Warnungen im Laufe der Zeit an.</span><span class="sxs-lookup"><span data-stu-id="9f133-156">**Alerts over time**—shows the number of related **Active** and **Resolved** alerts over time.</span></span> <span data-ttu-id="9f133-157">Die Anzahl der aufgelösten Warnungen gibt an, wie schnell Ihre Organisation auf Warnungen reagiert, die mit einer Bedrohung verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9f133-157">The number of resolved alerts indicates how quickly your organization responds to alerts associated with a threat.</span></span> <span data-ttu-id="9f133-158">Im Idealfall sollten im Diagramm Warnungen angezeigt werden, die innerhalb weniger Tage aufgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="9f133-158">Ideally, the chart should be showing alerts resolved within a few days.</span></span>
- <span data-ttu-id="9f133-159">**Betroffene Ressourcen**– zeigt die Anzahl der unterschiedlichen Geräte und E-Mail-Konten (Postfächer) an, denen derzeit mindestens eine aktive Warnung mit der nachverfolgten Bedrohung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="9f133-159">**Impacted assets**—shows the number of distinct devices and email accounts (mailboxes) that currently have at least one active alert associated with the tracked threat.</span></span> <span data-ttu-id="9f133-160">Warnungen werden für Postfächer ausgelöst, die Bedrohungs-E-Mails empfangen haben.</span><span class="sxs-lookup"><span data-stu-id="9f133-160">Alerts are triggered for mailboxes that received threat emails.</span></span> <span data-ttu-id="9f133-161">Überprüfen Sie sowohl die Organisations- als auch die Benutzerrichtlinien auf Außerkraftsetzungen, die die Zustellung von Bedrohungs-E-Mails verursachen.</span><span class="sxs-lookup"><span data-stu-id="9f133-161">Review both org- and user-level policies for overrides that cause the delivery of threat emails.</span></span>
- <span data-ttu-id="9f133-162">**Verhinderte E-Mail-Versuche**– zeigt die Anzahl der E-Mails aus den letzten sieben Tagen an, die entweder vor der Zustellung blockiert oder an den Junk-E-Mail-Ordner übermittelt wurden.</span><span class="sxs-lookup"><span data-stu-id="9f133-162">**Prevented email attempts**—shows the number of emails from the past seven days that were either blocked before delivery or delivered to the junk mail folder.</span></span>

#### <a name="review-security-resilience-and-posture"></a><span data-ttu-id="9f133-163">Überprüfen der Resilienz und des Sicherheitsstatus</span><span class="sxs-lookup"><span data-stu-id="9f133-163">Review security resilience and posture</span></span>

<span data-ttu-id="9f133-164">Jeder Bericht enthält Diagramme, die einen Überblick darüber bieten, wie stabil Ihre Organisation gegen eine bestimmte Bedrohung ist:</span><span class="sxs-lookup"><span data-stu-id="9f133-164">Each report includes charts that provide an overview of how resilient your organization is against a given threat:</span></span>

- <span data-ttu-id="9f133-165">Status der **sicheren Konfiguration**– zeigt die Anzahl der Geräte mit falsch konfigurierten Sicherheitseinstellungen an.</span><span class="sxs-lookup"><span data-stu-id="9f133-165">**Secure configuration status**—shows the number of devices with misconfigured security settings.</span></span> <span data-ttu-id="9f133-166">Wenden Sie die empfohlenen Sicherheitseinstellungen an, um die Bedrohung zu mindern.</span><span class="sxs-lookup"><span data-stu-id="9f133-166">Apply the recommended security settings to help mitigate the threat.</span></span> <span data-ttu-id="9f133-167">Geräte gelten als **sicher,** wenn _sie alle_ nachverfolgten Einstellungen angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="9f133-167">Devices are considered **Secure** if they have applied _all_ the tracked settings.</span></span>
- <span data-ttu-id="9f133-168">**Sicherheitsrisikopatchingstatus**– zeigt die Anzahl der anfälligen Geräte an.</span><span class="sxs-lookup"><span data-stu-id="9f133-168">**Vulnerability patching status**—shows the number of vulnerable devices.</span></span> <span data-ttu-id="9f133-169">Wenden Sie Sicherheitsupdates oder Patches an, um von der Bedrohung ausgenutzte Sicherheitsrisiken zu beheben.</span><span class="sxs-lookup"><span data-stu-id="9f133-169">Apply security updates or patches to address vulnerabilities exploited by the threat.</span></span>

#### <a name="view-reports-per-threat-tags"></a><span data-ttu-id="9f133-170">Anzeigen von Berichten pro Bedrohungstags</span><span class="sxs-lookup"><span data-stu-id="9f133-170">View reports per threat tags</span></span>

<span data-ttu-id="9f133-171">Sie können die Bedrohungsberichtsliste filtern und die relevantesten Berichte nach einem bestimmten Bedrohungstag (Kategorie) oder berichtstyp anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f133-171">You can filter the threat report list and view the most relevant reports according to a specific threat tag (category) or a report type.</span></span>

- <span data-ttu-id="9f133-172">**Bedrohungstags**– unterstützen Sie beim Anzeigen der relevantesten Berichte gemäß einer bestimmten Bedrohungskategorie.</span><span class="sxs-lookup"><span data-stu-id="9f133-172">**Threat tags**—assist you in viewing the most relevant reports according to a specific threat category.</span></span> <span data-ttu-id="9f133-173">Beispielsweise alle Berichte im Zusammenhang mit Ransomware.</span><span class="sxs-lookup"><span data-stu-id="9f133-173">For example, all reports related to ransomware.</span></span>
- <span data-ttu-id="9f133-174">**Berichtstypen**– unterstützen Sie beim Anzeigen der relevantesten Berichte gemäß einem bestimmten Berichtstyp.</span><span class="sxs-lookup"><span data-stu-id="9f133-174">**Report types**—assist you in viewing the most relevant reports according to a specific report type.</span></span> <span data-ttu-id="9f133-175">Beispielsweise alle Berichte, in denen Tools und Techniken behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="9f133-175">For example, all reports that cover tools and techniques.</span></span> 
- <span data-ttu-id="9f133-176">**Filter**– Unterstützen Sie bei der effizienten Überprüfung der Bedrohungsberichtsliste und beim Filtern der Ansicht anhand eines bestimmten Bedrohungstags oder Berichtstyps.</span><span class="sxs-lookup"><span data-stu-id="9f133-176">**Filters**—assist you in efficiently reviewing the threat report list and filtering the view based on a specific threat tag or report type.</span></span> <span data-ttu-id="9f133-177">Überprüfen Sie beispielsweise alle Bedrohungsberichte im Zusammenhang mit der Ransomware-Kategorie oder Bedrohungsberichte, die Sicherheitsrisiken abdecken.</span><span class="sxs-lookup"><span data-stu-id="9f133-177">For example, review all threat reports related to ransomware category, or threat reports that cover vulnerabilities.</span></span>

##### <a name="how-does-it-work"></a><span data-ttu-id="9f133-178">Wie funktioniert das?</span><span class="sxs-lookup"><span data-stu-id="9f133-178">How does it work?</span></span>

<span data-ttu-id="9f133-179">Das Microsoft Threat Intelligence-Team hat jedem Bedrohungsbericht Bedrohungstags hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="9f133-179">The Microsoft Threat Intelligence team has added threat tags to each threat report:</span></span>

- <span data-ttu-id="9f133-180">Vier Bedrohungstags sind jetzt verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9f133-180">Four threat tags are now available:</span></span>
  - <span data-ttu-id="9f133-181">Ransomware</span><span class="sxs-lookup"><span data-stu-id="9f133-181">Ransomware</span></span>
  - <span data-ttu-id="9f133-182">Phishing</span><span class="sxs-lookup"><span data-stu-id="9f133-182">Phishing</span></span>
  - <span data-ttu-id="9f133-183">Sicherheitsrisiko</span><span class="sxs-lookup"><span data-stu-id="9f133-183">Vulnerability</span></span>
  - <span data-ttu-id="9f133-184">Aktivitätsgruppe</span><span class="sxs-lookup"><span data-stu-id="9f133-184">Activity group</span></span>
- <span data-ttu-id="9f133-185">Bedrohungstags werden oben auf der Seite zur Bedrohungsanalyse mit Indikatoren für die Anzahl der verfügbaren Berichte unter jedem Tag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9f133-185">Threat tags are presented at the top of the threat analytics page, with counters for the number of available reports under each tag.</span></span>

  ![Bedrohungstags](../../media/threat-analytics/ta-threattags-mtp.png)

- <span data-ttu-id="9f133-187">Die Liste kann auch nach Bedrohungstags sortiert werden:</span><span class="sxs-lookup"><span data-stu-id="9f133-187">The list can also be sorted by threat tags:</span></span>

  ![lists](../../media/threat-analytics//ta-taglist-mtp.png)

- <span data-ttu-id="9f133-189">Filter sind pro Bedrohungstag und Berichtstyp verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9f133-189">Filters are available per threat tag and report type:</span></span>

  ![Filter](../../media/threat-analytics/ta-threattag-filters-mtp.png)

### <a name="analyst-report-get-expert-insight-from-microsoft-security-researchers"></a><span data-ttu-id="9f133-191">Analystenbericht: Abrufen von Experten-Einblicken von Microsoft-Sicherheitsexperten</span><span class="sxs-lookup"><span data-stu-id="9f133-191">Analyst report: Get expert insight from Microsoft security researchers</span></span>

<span data-ttu-id="9f133-192">Lesen Sie im Abschnitt **"Analystenbericht"** den detaillierten Expertenbericht.</span><span class="sxs-lookup"><span data-stu-id="9f133-192">In the **Analyst report** section, read through the detailed expert write-up.</span></span> <span data-ttu-id="9f133-193">Die meisten Berichte enthalten detaillierte Beschreibungen von Angriffsketten, einschließlich Taktiken und Techniken, die dem MITRE ATT&CK-Framework zugeordnet sind, vollständige Listen mit Empfehlungen und leistungsstarke Anleitungen zur [Bedrohungssuche.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9f133-193">Most reports provide detailed descriptions of attack chains, including tactics and techniques mapped to the MITRE ATT&CK framework, exhaustive lists of recommendations, and powerful [threat hunting](advanced-hunting-overview.md) guidance.</span></span>

[<span data-ttu-id="9f133-194">Weitere Informationen zum Analystenbericht</span><span class="sxs-lookup"><span data-stu-id="9f133-194">Learn more about the analyst report</span></span>](threat-analytics-analyst-reports.md)

### <a name="related-incidents-view-and-manage-related-incidents"></a><span data-ttu-id="9f133-195">Verwandte Vorfälle: Anzeigen und Verwalten verwandter Vorfälle</span><span class="sxs-lookup"><span data-stu-id="9f133-195">Related incidents: View and manage related incidents</span></span>

<span data-ttu-id="9f133-196">Die Registerkarte **"Verwandte Vorfälle"** enthält die Liste aller Vorfälle im Zusammenhang mit der nachverfolgten Bedrohung.</span><span class="sxs-lookup"><span data-stu-id="9f133-196">The **Related incidents** tab provides the list of all incidents related to the tracked threat.</span></span> <span data-ttu-id="9f133-197">Sie können Vorfälle zuweisen oder Warnungen verwalten, die mit jedem Vorfall verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="9f133-197">You can assign incidents or manage alerts linked to each incident.</span></span> 


![Abbildung des Abschnitts zu verwandten Vorfällen eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_related_incidents_mtp.png)

<span data-ttu-id="9f133-199">_Abschnitt "Verwandte Vorfälle" eines Berichts zur Bedrohungsanalyse_</span><span class="sxs-lookup"><span data-stu-id="9f133-199">_Related incidents section of a threat analytics report_</span></span>

### <a name="impacted-assets-get-list-of-impacted-devices-and-mailboxes"></a><span data-ttu-id="9f133-200">Betroffene Ressourcen: Abrufen einer Liste betroffener Geräte und Postfächer</span><span class="sxs-lookup"><span data-stu-id="9f133-200">Impacted assets: Get list of impacted devices and mailboxes</span></span>

<span data-ttu-id="9f133-201">Eine Ressource gilt als betroffen, wenn sie von einer aktiven, nicht aufgelösten Warnung betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="9f133-201">An asset is considered impacted if it is affected by an active, unresolved alert.</span></span> <span data-ttu-id="9f133-202">Auf der Registerkarte **"Betroffene Objekte"** sind die folgenden Arten von betroffenen Ressourcen aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="9f133-202">The **Impacted assets** tab lists the following types of impacted assets:</span></span>

- <span data-ttu-id="9f133-203">**Betroffene Geräte**– Endpunkte mit nicht aufgelösten Microsoft Defender für Endpunkt-Warnungen.</span><span class="sxs-lookup"><span data-stu-id="9f133-203">**Impacted devices**—endpoints that have unresolved Microsoft Defender for Endpoint alerts.</span></span> <span data-ttu-id="9f133-204">Diese Warnungen werden in der Regel bei Sichtung bekannter Bedrohungsindikatoren und -aktivitäten ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="9f133-204">These alerts typically fire on sightings of known threat indicators and activities.</span></span>
- <span data-ttu-id="9f133-205">**Betroffene Postfächer**– Postfächer, die E-Mail-Nachrichten empfangen haben, die Microsoft Defender für Office 365 Warnungen ausgelöst haben.</span><span class="sxs-lookup"><span data-stu-id="9f133-205">**Impacted mailboxes**—mailboxes that have received email messages that have triggered Microsoft Defender for Office 365 alerts.</span></span> <span data-ttu-id="9f133-206">Während die meisten Nachrichten, die Warnungen auslösen, in der Regel blockiert werden, können Richtlinien auf Benutzer- oder Organisationsebene Filter außer Kraft setzen.</span><span class="sxs-lookup"><span data-stu-id="9f133-206">While most messages that trigger alerts are typically blocked, user- or org-level policies can override filters.</span></span>

![Abbildung des Abschnitts "Betroffene Ressourcen" eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_impacted_assets_mtp.png)

<span data-ttu-id="9f133-208">_Abschnitt "Betroffene Ressourcen" eines Bedrohungsanalyseberichts_</span><span class="sxs-lookup"><span data-stu-id="9f133-208">_Impacted assets section of a threat analytics report_</span></span>

### <a name="prevented-email-attempts-view-blocked-or-junked-threat-emails"></a><span data-ttu-id="9f133-209">Verhinderte E-Mail-Versuche: Blockierte oder Junk-Bedrohungs-E-Mails anzeigen</span><span class="sxs-lookup"><span data-stu-id="9f133-209">Prevented email attempts: View blocked or junked threat emails</span></span>

<span data-ttu-id="9f133-210">Microsoft Defender für Office 365 blockiert in der Regel E-Mails mit bekannten Bedrohungsindikatoren, einschließlich bösartiger Links oder Anlagen.</span><span class="sxs-lookup"><span data-stu-id="9f133-210">Microsoft Defender for Office 365 typically blocks emails with known threat indicators, including malicious links or attachments.</span></span> <span data-ttu-id="9f133-211">In einigen Fällen senden proaktive Filtermechanismen, die auf verdächtige Inhalte prüfen, stattdessen Bedrohungs-E-Mails an den Junk-E-Mail-Ordner.</span><span class="sxs-lookup"><span data-stu-id="9f133-211">In some cases, proactive filtering mechanisms that check for suspicious content will instead send threat emails to the junk mail folder.</span></span> <span data-ttu-id="9f133-212">In beiden Fällen ist die Wahrscheinlichkeit, dass Schadsoftwarecode auf dem Gerät gestartet wird, geringer.</span><span class="sxs-lookup"><span data-stu-id="9f133-212">In either case, the chances of the threat launching malware code on the device is reduced.</span></span>

<span data-ttu-id="9f133-213">Die Registerkarte **"Verhinderte E-Mail-Versuche" listet** alle E-Mails auf, die entweder vor der Zustellung blockiert oder von Microsoft Defender für Office 365 an den Junk-E-Mail-Ordner gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="9f133-213">The **Prevented email attempts** tab lists all the emails that have either been blocked before delivery or sent to the junk mail folder by Microsoft Defender for Office 365.</span></span> 

![Abbildung des Abschnitts "Verhinderte E-Mail-Versuche" eines Bedrohungsanalyseberichts](../../media/threat-analytics/ta_prevented_email_attempts_mtp.png)

<span data-ttu-id="9f133-215">_Abschnitt "Verhinderte E-Mail-Versuche" eines Bedrohungsanalyseberichts_</span><span class="sxs-lookup"><span data-stu-id="9f133-215">_Prevented email attempts section of a threat analytics report_</span></span>

### <a name="mitigations-review-list-of-mitigations-and-the-status-of-your-devices"></a><span data-ttu-id="9f133-216">Gegenmaßnahmen: Überprüfen der Liste der Gegenmaßnahmen und des Status Ihrer Geräte</span><span class="sxs-lookup"><span data-stu-id="9f133-216">Mitigations: Review list of mitigations and the status of your devices</span></span>

<span data-ttu-id="9f133-217">Überprüfen Sie im Abschnitt **"Gegenmaßnahmen"** die Liste der spezifischen Empfehlungen, die Sie bei der Verbesserung der Ausfallsicherheit Ihrer Organisation gegen die Bedrohung unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="9f133-217">In the **Mitigations** section, review the list of specific actionable recommendations that can help you increase your organizational resilience against the threat.</span></span> <span data-ttu-id="9f133-218">Die Liste der nachverfolgten Gegenmaßnahmen umfasst:</span><span class="sxs-lookup"><span data-stu-id="9f133-218">The list of tracked mitigations includes:</span></span>

- <span data-ttu-id="9f133-219">**Sicherheitsupdates**– Bereitstellung unterstützter Software-Sicherheitsupdates für Sicherheitsrisiken, die auf integrierten Geräten gefunden werden</span><span class="sxs-lookup"><span data-stu-id="9f133-219">**Security updates**—deployment of supported software security updates for vulnerabilities found on onboarded devices</span></span>
- <span data-ttu-id="9f133-220">**Unterstützte Sicherheitskonfigurationen**</span><span class="sxs-lookup"><span data-stu-id="9f133-220">**Supported security configurations**</span></span>
  - <span data-ttu-id="9f133-221">Aus der Cloud gelieferter Schutz</span><span class="sxs-lookup"><span data-stu-id="9f133-221">Cloud-delivered protection</span></span>  
  - <span data-ttu-id="9f133-222">Schutz vor potenziell unerwünschten Anwendungen (PUA)</span><span class="sxs-lookup"><span data-stu-id="9f133-222">Potentially unwanted application (PUA) protection</span></span>
  - <span data-ttu-id="9f133-223">Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="9f133-223">Real-time protection</span></span>

<span data-ttu-id="9f133-224">Die Schadensbegrenzungsinformationen in diesem Abschnitt enthalten Daten aus [Bedrohungs- und Sicherheitsrisikomanagement,](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)die auch detaillierte Drilldowninformationen von verschiedenen Links im Bericht enthalten.</span><span class="sxs-lookup"><span data-stu-id="9f133-224">Mitigation information in this section incorporates data from [threat and vulnerability management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt), which also provides detailed drill-down information from various links in the report.</span></span>

![Abbildung des Abschnitts "Risikominderungen" eines Bedrohungsanalyseberichts mit sicheren Konfigurationsdetails](../../media/threat-analytics/ta_mitigations_mtp.png)

![Abbildung des Abschnitts "Risikominderungen" eines Bedrohungsanalyseberichts mit Details zu Sicherheitsrisiken](../../media/threat-analytics/ta_mitigations_mtp2.png)

<span data-ttu-id="9f133-227">_Abschnitt "Risikominderungen" eines Berichts zur Bedrohungsanalyse_</span><span class="sxs-lookup"><span data-stu-id="9f133-227">_Mitigations section of a threat analytics report_</span></span>

## <a name="additional-report-details-and-limitations"></a><span data-ttu-id="9f133-228">Zusätzliche Berichtsdetails und Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="9f133-228">Additional report details and limitations</span></span>

> [!NOTE]
> <span data-ttu-id="9f133-229">Im Rahmen der einheitlichen Sicherheitsumgebung ist die Bedrohungsanalyse jetzt nicht nur für Microsoft Defender für Endpunkt, sondern auch für Microsoft Defender für Office E5-Lizenzinhaber verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9f133-229">As part of the unified security experience, threat analytics is now available not just for Microsoft Defender for Endpoint, but also for Microsoft Defender for Office E5 license holders.</span></span>
>
> <span data-ttu-id="9f133-230">Wenn Sie das Microsoft 365 Sicherheitsportal (Microsoft 365 Defender) nicht verwenden, können Sie auch die Berichtsdetails (ohne Microsoft Defender für Office Daten) im Microsoft Defender Security Center-Portal (Microsoft Defender für Endpunkt) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9f133-230">If you are not using the Microsoft 365 security portal (Microsoft 365 Defender), you can also see the report details (without the Microsoft Defender for Office data) in the Microsoft Defender Security Center portal (Microsoft Defender for Endpoint).</span></span>

<span data-ttu-id="9f133-231">Für den Zugriff auf den Bericht zur Bedrohungsanalyse benötigen Sie bestimmte Rollen und Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="9f133-231">To access threat analytics report you need certain roles and permissions.</span></span> <span data-ttu-id="9f133-232">Weitere Informationen finden Sie [unter "Benutzerdefinierte Rollen in der rollenbasierten Zugriffssteuerung" für Microsoft 365 Defender.](custom-roles.md)</span><span class="sxs-lookup"><span data-stu-id="9f133-232">See [Custom roles in role-based access control for Microsoft 365 Defender](custom-roles.md) for details.</span></span>

- <span data-ttu-id="9f133-233">Um Warnungen, Vorfälle oder betroffene Ressourcendaten anzuzeigen, benötigen Sie Berechtigungen für Microsoft Defender für Office- oder Microsoft Defender für Endpunkt-Warnungsdaten oder beides.</span><span class="sxs-lookup"><span data-stu-id="9f133-233">To view alerts, incidents, or impacted assets data, you need to have permissions to Microsoft Defender for Office or Microsoft Defender for Endpoint alerts data, or both.</span></span>
- <span data-ttu-id="9f133-234">Um verhinderte E-Mail-Versuche anzuzeigen, benötigen Sie Berechtigungen für Microsoft Defender für Office-Suchdaten.</span><span class="sxs-lookup"><span data-stu-id="9f133-234">To view prevented email attempts, you need to have permissions to Microsoft Defender for Office hunting data.</span></span> 
- <span data-ttu-id="9f133-235">Zum Anzeigen von Gegenmaßnahmen benötigen Sie Berechtigungen zum Bedrohungs- und Sicherheitsrisikomanagement von Daten in Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="9f133-235">To view mitigations, you need to have permissions to threat and vulnerability management data in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="9f133-236">Beachten Sie beim Betrachten der Daten zur Bedrohungsanalyse die folgenden Faktoren:</span><span class="sxs-lookup"><span data-stu-id="9f133-236">When looking at the threat analytics data, remember the following factors:</span></span>

- <span data-ttu-id="9f133-237">Diagramme enthalten nur Gegenmaßnahmen, die nachverfolgt werden.</span><span class="sxs-lookup"><span data-stu-id="9f133-237">Charts reflect only mitigations that are tracked.</span></span> <span data-ttu-id="9f133-238">In der Berichtsübersicht finden Sie weitere Gegenmaßnahmen, die nicht in den Diagrammen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f133-238">Check the report overview for additional mitigations that are not shown in the charts.</span></span>
- <span data-ttu-id="9f133-239">Risikominderungen bieten keine Garantie für vollständige Resilienz.</span><span class="sxs-lookup"><span data-stu-id="9f133-239">Mitigations don't guarantee complete resilience.</span></span> <span data-ttu-id="9f133-240">Die bereitgestellten Gegenmaßnahmen spiegeln die bestmöglichen Maßnahmen wider, die zur Verbesserung der Resilienz erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9f133-240">The provided mitigations reflect the best possible actions needed to improve resiliency.</span></span>
- <span data-ttu-id="9f133-241">Geräte werden als "nicht verfügbar" gezählt, wenn sie keine Daten an den Dienst übertragen haben.</span><span class="sxs-lookup"><span data-stu-id="9f133-241">Devices are counted as "unavailable" if they have not transmitted data to the service.</span></span>
- <span data-ttu-id="9f133-242">Antivirusbezogene Statistiken basieren auf Microsoft Defender Antivirus Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="9f133-242">Antivirus-related statistics are based on Microsoft Defender Antivirus settings.</span></span> <span data-ttu-id="9f133-243">Geräte mit Antivirenlösungen von Drittanbietern können als "verfügbar gemacht" angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9f133-243">Devices with third-party antivirus solutions can appear as "exposed".</span></span>

## <a name="related-topics"></a><span data-ttu-id="9f133-244">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9f133-244">Related topics</span></span>

- [<span data-ttu-id="9f133-245">Proaktive Suche nach Bedrohungen mit erweiterter Suche</span><span class="sxs-lookup"><span data-stu-id="9f133-245">Proactively find threats with advanced hunting</span></span>](advanced-hunting-overview.md) 
- [<span data-ttu-id="9f133-246">Grundlegendes zum Abschnitt "Analystenbericht"</span><span class="sxs-lookup"><span data-stu-id="9f133-246">Understand the analyst report section</span></span>](threat-analytics-analyst-reports.md)
- [<span data-ttu-id="9f133-247">Bewerten und Beheben von Sicherheitsschwächen und Gefährdungen</span><span class="sxs-lookup"><span data-stu-id="9f133-247">Assess and resolve security weaknesses and exposures</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)

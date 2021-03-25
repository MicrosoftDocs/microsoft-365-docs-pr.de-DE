---
title: Ereigniszeitachse im Bedrohungs- und Sicherheitsrisikomanagement
description: Die Ereigniszeitachse ist ein Newsfeed für Risiken, mit dem Sie interpretieren können, wie Risiken in die Organisation eingeführt werden und welche Gegenmaßnahmen zur Reduzierung des Risikos eingetreten sind.
keywords: Ereigniszeitachse, mdatp-Ereigniszeitachse, mdatp tvm-Ereigniszeitachse, Bedrohungs- und Sicherheitsrisikoverwaltung, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5532e9058d7a49033f651e3fbee605e5ae39d05a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068807"
---
# <a name="event-timeline---threat-and-vulnerability-management"></a><span data-ttu-id="31589-104">Ereigniszeitachse – Bedrohungs- und Sicherheitsrisikoverwaltung</span><span class="sxs-lookup"><span data-stu-id="31589-104">Event timeline - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="31589-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="31589-105">**Applies to:**</span></span>
- [<span data-ttu-id="31589-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="31589-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="31589-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="31589-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="31589-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="31589-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="31589-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="31589-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

<span data-ttu-id="31589-110">Die Ereigniszeitachse ist ein Newsfeed für Risiken, mit dem Sie interpretieren können, wie Risiken durch neue Sicherheitsrisiken oder Exploits in die Organisation eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="31589-110">Event timeline is a risk news feed that helps you interpret how risk is introduced into the organization through new vulnerabilities or exploits.</span></span> <span data-ttu-id="31589-111">Sie können Ereignisse anzeigen, die sich auf das Risiko Ihrer Organisation auswirken können.</span><span class="sxs-lookup"><span data-stu-id="31589-111">You can view events that may impact your organization's risk.</span></span> <span data-ttu-id="31589-112">Beispielsweise finden Sie neue Sicherheitsrisiken, die eingeführt wurden, Sicherheitsrisiken, die ausgenutzt werden konnten, Exploits, die einem Exploit Kit hinzugefügt wurden, und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="31589-112">For example, you can find new vulnerabilities that were introduced, vulnerabilities that became exploitable, exploit that was added to an exploit kit, and more.</span></span>

<span data-ttu-id="31589-113">Die Ereigniszeitachse enthält [](tvm-exposure-score.md) außerdem die Geschichte ihrer Belichtungsergebnis und [der Microsoft Secure Score für](tvm-microsoft-secure-score-devices.md) Geräte, damit Sie die Ursache für große Änderungen ermitteln können.</span><span class="sxs-lookup"><span data-stu-id="31589-113">Event timeline also tells the story of your [exposure score](tvm-exposure-score.md) and [Microsoft Secure Score for Devices](tvm-microsoft-secure-score-devices.md) so you can determine the cause of large changes.</span></span> <span data-ttu-id="31589-114">Ereignisse können sich auf Ihre Geräte oder Ihre Bewertung für Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="31589-114">Events can impact your devices or your score for devices.</span></span> <span data-ttu-id="31589-115">Reduzieren Sie Ihre Risikoposition, indem Sie auf der Grundlage der priorisierten Sicherheitsempfehlungen das problembearbeiten, [was behoben werden muss.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="31589-115">Reduce you exposure by addressing what needs to be remediated based on the prioritized [security recommendations](tvm-security-recommendation.md).</span></span>

>[!TIP]
><span data-ttu-id="31589-116">Informationen zu E-Mails zu neuen Sicherheitsrisikoereignissen finden Sie unter [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="31589-116">To get emails about new vulnerability events, see [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)</span></span>

## <a name="navigate-to-the-event-timeline-page"></a><span data-ttu-id="31589-117">Navigieren zur Seite Ereigniszeitachse</span><span class="sxs-lookup"><span data-stu-id="31589-117">Navigate to the Event timeline page</span></span>

<span data-ttu-id="31589-118">Es gibt auch drei Einstiegspunkte aus dem Dashboard zur Verwaltung von Bedrohungen und [Sicherheitslücken:](tvm-dashboard-insights.md)</span><span class="sxs-lookup"><span data-stu-id="31589-118">There are also three entry points from the [threat and vulnerability management dashboard](tvm-dashboard-insights.md):</span></span>

- <span data-ttu-id="31589-119">**Belichtungsergebniskarte** der Organisation: Zeigen Sie im Diagramm "Belichtungsergebnis im Laufe der Zeit" auf die Ereignispunkte, und wählen Sie "Alle Ereignisse von diesem Tag anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="31589-119">**Organization exposure score card**: Hover over the event dots in the "Exposure Score over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="31589-120">Die Ereignisse stellen Softwarerisiken dar.</span><span class="sxs-lookup"><span data-stu-id="31589-120">The events represent software vulnerabilities.</span></span>
- <span data-ttu-id="31589-121">**Microsoft Secure Score for Devices**: Zeigen Sie im Diagramm "Ihre Bewertung für Geräte im Laufe der Zeit" auf die Ereignispunkte, und wählen Sie "Alle Ereignisse von diesem Tag anzeigen" aus.</span><span class="sxs-lookup"><span data-stu-id="31589-121">**Microsoft Secure Score for Devices**: Hover over the event dots in the "Your score for devices over time" graph and select "See all events from this day."</span></span> <span data-ttu-id="31589-122">Die Ereignisse stellen neue Konfigurationsbewertungen dar.</span><span class="sxs-lookup"><span data-stu-id="31589-122">The events represent new configuration assessments.</span></span>
- <span data-ttu-id="31589-123">**Karte "Top-Ereignisse":** Wählen Sie "Weitere Anzeigen" unten in der Tabelle "Top Events" aus.</span><span class="sxs-lookup"><span data-stu-id="31589-123">**Top events card**: Select "Show more" at the bottom of the top events table.</span></span> <span data-ttu-id="31589-124">Die Karte zeigt die drei auswirkungenreichsten Ereignisse der letzten 7 Tage an.</span><span class="sxs-lookup"><span data-stu-id="31589-124">The card displays the three most impactful events in the last 7 days.</span></span> <span data-ttu-id="31589-125">Zu den auswirkungenreichen Ereignissen kann gehören, wenn sich das Ereignis auf eine große Anzahl von Geräten auswirkt oder wenn es sich um eine kritische Sicherheitslücke handelt.</span><span class="sxs-lookup"><span data-stu-id="31589-125">Impactful events can include if the event affects a large number of devices, or if it is a critical vulnerability.</span></span>

### <a name="exposure-score-and-microsoft-secure-score-for-devices-graphs"></a><span data-ttu-id="31589-126">Belichtungsergebnis und Microsoft Secure Score for Devices Graphs</span><span class="sxs-lookup"><span data-stu-id="31589-126">Exposure score and Microsoft Secure Score for Devices graphs</span></span>

<span data-ttu-id="31589-127">Zeigen Sie im Dashboard für die Bedrohungs- und Sicherheitsrisikoverwaltung auf das Diagramm Belichtungsergebnis, um die top-Software-Sicherheitsrisikoereignisse von diesem Tag anzuzeigen, die sich auf Ihre Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="31589-127">In the threat and vulnerability management dashboard, hover over the Exposure score graph to view top software vulnerability events from that day that impacted your devices.</span></span> <span data-ttu-id="31589-128">Zeigen Sie auf das Microsoft Secure Score for Devices-Diagramm, um neue Sicherheitskonfigurationsbewertungen anzuzeigen, die sich auf Ihre Bewertung auswirken.</span><span class="sxs-lookup"><span data-stu-id="31589-128">Hover over the Microsoft Secure Score for Devices graph to view new security configuration assessments that affect your score.</span></span>

<span data-ttu-id="31589-129">Wenn es keine Ereignisse gibt, die sich auf Ihre Geräte oder Ihre Bewertung für Geräte auswirken, wird keines angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31589-129">If there are no events that affect your devices or your score for devices, then none will be shown.</span></span>

<span data-ttu-id="31589-130">![Belichtungsergebnis mit ](images/tvm-event-timeline-exposure-score350.png) 
 ![ Dem Mauszeiger microsoft Secure Score for Devices](images/tvm-event-timeline-device-hover360.png)</span><span class="sxs-lookup"><span data-stu-id="31589-130">![Exposure score hover](images/tvm-event-timeline-exposure-score350.png) 
![Microsoft Secure Score for Devices hover](images/tvm-event-timeline-device-hover360.png)</span></span>

### <a name="drill-down-to-events-from-that-day"></a><span data-ttu-id="31589-131">Drilldown zu Ereignissen von diesem Tag</span><span class="sxs-lookup"><span data-stu-id="31589-131">Drill down to events from that day</span></span>

<span data-ttu-id="31589-132">Wenn Sie alle Ereignisse von diesem Tag anzeigen **auswählen,** gelangen Sie zur Seite Ereigniszeitachse mit einem benutzerdefinierten Datumsbereich für diesen Tag.</span><span class="sxs-lookup"><span data-stu-id="31589-132">Selecting **Show all events from this day** takes you to the Event timeline page with a custom date range for that day.</span></span>

![Ereigniszeitachse ausgewählter benutzerdefinierter Datumsbereich](images/tvm-event-timeline-drilldown.png)

<span data-ttu-id="31589-134">Wählen **Sie Benutzerdefinierter** Bereich aus, um den Datumsbereich in einen anderen benutzerdefinierten oder einen vordefinierten Zeitraum zu ändern.</span><span class="sxs-lookup"><span data-stu-id="31589-134">Select **Custom range** to change the date range to another custom one, or a pre-set time range.</span></span>

![Optionen für den Datumsbereich der Ereigniszeitachse](images/tvm-event-timeline-dates.png)

## <a name="event-timeline-overview"></a><span data-ttu-id="31589-136">Übersicht über die Ereigniszeitachse</span><span class="sxs-lookup"><span data-stu-id="31589-136">Event timeline overview</span></span>

<span data-ttu-id="31589-137">Auf der Seite Ereigniszeitachse können Sie alle erforderlichen Informationen zu einem Ereignis anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31589-137">On the Event timeline page, you can view the all the necessary info related to an event.</span></span> 

<span data-ttu-id="31589-138">Features:</span><span class="sxs-lookup"><span data-stu-id="31589-138">Features:</span></span>

- <span data-ttu-id="31589-139">Anpassen von Spalten</span><span class="sxs-lookup"><span data-stu-id="31589-139">Customize columns</span></span>
- <span data-ttu-id="31589-140">Filtern nach Ereignistyp oder Prozent der betroffener Geräte</span><span class="sxs-lookup"><span data-stu-id="31589-140">Filter by event type or percent of impacted devices</span></span>
- <span data-ttu-id="31589-141">Anzeigen von 30, 50 oder 100 Elementen pro Seite</span><span class="sxs-lookup"><span data-stu-id="31589-141">View 30, 50, or 100 items per page</span></span>

<span data-ttu-id="31589-142">Die beiden großen Zahlen oben auf der Seite zeigen die Anzahl neuer Sicherheitsrisiken und ausnutzende Sicherheitsrisiken an, nicht Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="31589-142">The two large numbers at the top of the page show the number of new vulnerabilities and exploitable vulnerabilities, not events.</span></span> <span data-ttu-id="31589-143">Einige Ereignisse können mehrere Sicherheitsrisiken aufweisen, und einige Sicherheitsrisiken können mehrere Ereignisse aufweisen.</span><span class="sxs-lookup"><span data-stu-id="31589-143">Some events can have multiple vulnerabilities, and some vulnerabilities can have multiple events.</span></span>

![Ereigniszeitachsenseite](images/tvm-event-timeline-overview-mixed-type.png)

### <a name="columns"></a><span data-ttu-id="31589-145">Spalten</span><span class="sxs-lookup"><span data-stu-id="31589-145">Columns</span></span>

- <span data-ttu-id="31589-146">**Datum**: Monat, Tag, Jahr</span><span class="sxs-lookup"><span data-stu-id="31589-146">**Date**: month, day, year</span></span>
- <span data-ttu-id="31589-147">**Ereignis**: Auswirkungsereignis, einschließlich Komponente, Typ und Anzahl betroffener Geräte</span><span class="sxs-lookup"><span data-stu-id="31589-147">**Event**: impactful event, including component, type, and number of impacted devices</span></span>
- <span data-ttu-id="31589-148">**Verwandte Komponente**: Software</span><span class="sxs-lookup"><span data-stu-id="31589-148">**Related component**: software</span></span>
- <span data-ttu-id="31589-149">**Ursprünglich betroffener Geräte:** Die Anzahl und der Prozentsatz betroffener Geräte, als dieses Ereignis ursprünglich aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="31589-149">**Originally impacted devices**: the number, and percentage, of impacted devices when this event originally occurred.</span></span> <span data-ttu-id="31589-150">Sie können auch nach dem Prozent der ursprünglich betroffenen Geräte filtern, und die Gesamtzahl der Geräte.</span><span class="sxs-lookup"><span data-stu-id="31589-150">You can also filter by the percent of originally impacted devices, out of your total number of devices.</span></span>
- <span data-ttu-id="31589-151">**Aktuell betroffener Geräte:** die aktuelle Anzahl und der Prozentsatz der Geräte, die dieses Ereignis derzeit beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="31589-151">**Currently impacted devices**: the current number, and percentage, of devices that this event currently impacts.</span></span> <span data-ttu-id="31589-152">Sie finden dieses Feld, indem Sie **Spalten anpassen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="31589-152">You can find this field by selecting **Customize columns**.</span></span>
- <span data-ttu-id="31589-153">**Typen**: spiegeln Zeitstempelereignisse wider, die sich auf die Bewertung auswirken.</span><span class="sxs-lookup"><span data-stu-id="31589-153">**Types**: reflect time-stamped events that impact the score.</span></span> <span data-ttu-id="31589-154">Sie können gefiltert werden.</span><span class="sxs-lookup"><span data-stu-id="31589-154">They can be filtered.</span></span>
    - <span data-ttu-id="31589-155">Einem Exploitkit hinzugefügter Exploit</span><span class="sxs-lookup"><span data-stu-id="31589-155">Exploit added to an exploit kit</span></span>
    - <span data-ttu-id="31589-156">Exploit wurde überprüft</span><span class="sxs-lookup"><span data-stu-id="31589-156">Exploit was verified</span></span>
    - <span data-ttu-id="31589-157">Neuer öffentlicher Exploit</span><span class="sxs-lookup"><span data-stu-id="31589-157">New public exploit</span></span>
    - <span data-ttu-id="31589-158">Neue Sicherheitslücke</span><span class="sxs-lookup"><span data-stu-id="31589-158">New vulnerability</span></span>
    - <span data-ttu-id="31589-159">Neue Konfigurationsbewertung</span><span class="sxs-lookup"><span data-stu-id="31589-159">New configuration assessment</span></span>
- <span data-ttu-id="31589-160">**Bewertungstrend**: Belichtungsergebnistrend</span><span class="sxs-lookup"><span data-stu-id="31589-160">**Score trend**: exposure score trend</span></span>

### <a name="icons"></a><span data-ttu-id="31589-161">Symbole</span><span class="sxs-lookup"><span data-stu-id="31589-161">Icons</span></span>

<span data-ttu-id="31589-162">Die folgenden Symbole werden neben Ereignissen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="31589-162">The following icons show up next to events:</span></span>

- ![Fehlersymbol](images/tvm-black-bug-icon.png) <span data-ttu-id="31589-164">Neuer öffentlicher Exploit</span><span class="sxs-lookup"><span data-stu-id="31589-164">New public exploit</span></span>
- ![Symbol für Berichtswarnung](images/report-warning-icon.png) <span data-ttu-id="31589-166">Neue Sicherheitslücke wurde veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="31589-166">New vulnerability was published</span></span>
- ![Exploit Kit](images/bug-lightning-icon2.png) <span data-ttu-id="31589-168">Exploit im Exploit Kit</span><span class="sxs-lookup"><span data-stu-id="31589-168">Exploit found in exploit kit</span></span>
- ![Fehlersymbol mit Warnungssymbol](images/bug-caution-icon2.png) <span data-ttu-id="31589-170">Exploit überprüft</span><span class="sxs-lookup"><span data-stu-id="31589-170">Exploit verified</span></span>

### <a name="drill-down-to-a-specific-event"></a><span data-ttu-id="31589-171">Drilldown zu einem bestimmten Ereignis</span><span class="sxs-lookup"><span data-stu-id="31589-171">Drill down to a specific event</span></span>

<span data-ttu-id="31589-172">Nachdem Sie ein Ereignis ausgewählt haben, wird ein Flyout mit einer Liste der Details und aktuellen CVEs angezeigt, die sich auf Ihre Geräte auswirken.</span><span class="sxs-lookup"><span data-stu-id="31589-172">Once you select an event, a flyout will appear with a list of the details and current CVEs that affect your devices.</span></span> <span data-ttu-id="31589-173">Sie können weitere CVEs anzeigen oder die zugehörige Empfehlung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31589-173">You can show more CVEs or view the related recommendation.</span></span>

<span data-ttu-id="31589-174">Der Pfeil unter "Bewertungstrend" hilft Ihnen zu bestimmen, ob dieses Ereignis ihre belichtungsbedingte Bewertung möglicherweise ausgelöst oder gesenkt hat.</span><span class="sxs-lookup"><span data-stu-id="31589-174">The arrow below "score trend" helps you determine whether this event potentially raised or lowered your organizational exposure score.</span></span> <span data-ttu-id="31589-175">Eine höhere Belichtungszahl bedeutet, dass Geräte anfälliger für die Nutzung sind.</span><span class="sxs-lookup"><span data-stu-id="31589-175">Higher exposure score means devices are more vulnerable to exploitation.</span></span>

![Flyout der Ereigniszeitachse](images/tvm-event-timeline-flyout500.png)

<span data-ttu-id="31589-177">Wählen Sie von dort **auf der** Seite Sicherheitsempfehlungen die Option Zu zugehöriger Sicherheitsempfehlung wechseln die Empfehlung aus, die die neue Sicherheitslücke der Software [behebt.](tvm-security-recommendation.md)</span><span class="sxs-lookup"><span data-stu-id="31589-177">From there, select **Go to related security recommendation** view the recommendation that addresses the new software vulnerability in the [security recommendations page](tvm-security-recommendation.md).</span></span> <span data-ttu-id="31589-178">Nachdem Sie die Beschreibung und die Sicherheitsrisikodetails in der Sicherheitsempfehlung gelesen haben, können Sie eine Korrekturanforderung übermitteln und die Anforderung auf der Seite "Problembehebung" [nachverfolgen.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="31589-178">After reading the description and vulnerability details in the security recommendation, you can submit a remediation request, and track the request in the [remediation page](tvm-remediation.md).</span></span>  

## <a name="view-event-timelines-in-software-pages"></a><span data-ttu-id="31589-179">Anzeigen von Ereigniszeitachsen auf Softwareseiten</span><span class="sxs-lookup"><span data-stu-id="31589-179">View Event timelines in software pages</span></span>

<span data-ttu-id="31589-180">Wählen Sie zum Öffnen einer Softwareseite ein Ereignis aus, > im Flyout den Namen der mit Hyperlinks verknüpften Software (wie Visual Studio 2017) im Abschnitt "Verwandte Komponente" auswählen.</span><span class="sxs-lookup"><span data-stu-id="31589-180">To open a software page, select an event > select the hyperlinked software name (like Visual Studio 2017) in the section called "Related component" in the flyout.</span></span> [<span data-ttu-id="31589-181">Weitere Informationen zu Softwareseiten</span><span class="sxs-lookup"><span data-stu-id="31589-181">Learn more about software pages</span></span>](tvm-software-inventory.md#software-pages)

<span data-ttu-id="31589-182">Eine vollständige Seite mit allen Details einer bestimmten Software wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31589-182">A full page will appear with all the details of a specific software.</span></span> <span data-ttu-id="31589-183">Bewegen Sie die Maus über das Diagramm, um die Zeitachse der Ereignisse für diese bestimmte Software anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31589-183">Mouse over the graph to see the timeline of events for that specific software.</span></span>

![Softwareseite mit einem Ereigniszeitachsendiagramm](images/tvm-event-timeline-software2.png)

<span data-ttu-id="31589-185">Navigieren Sie zur Registerkarte Ereigniszeitachse, um alle Ereignisse im Zusammenhang mit dieser Software anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31589-185">Navigate to the event timeline tab to view all the events related to that software.</span></span> <span data-ttu-id="31589-186">Sie können auch Sicherheitsempfehlungen, ermittelte Sicherheitsrisiken, installierte Geräte und Versionsverteilung sehen.</span><span class="sxs-lookup"><span data-stu-id="31589-186">You can also see security recommendations, discovered vulnerabilities, installed devices, and version distribution.</span></span>

![Softwareseite mit registerkarte Ereigniszeitachse](images/tvm-event-timeline-software-pages.png)

## <a name="related-topics"></a><span data-ttu-id="31589-188">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="31589-188">Related topics</span></span>

- [<span data-ttu-id="31589-189">Übersicht über die Verwaltung von Bedrohungen und Sicherheitslücken</span><span class="sxs-lookup"><span data-stu-id="31589-189">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="31589-190">Dashboard</span><span class="sxs-lookup"><span data-stu-id="31589-190">Dashboard</span></span>](tvm-dashboard-insights.md)
- [<span data-ttu-id="31589-191">Belichtungsergebnis</span><span class="sxs-lookup"><span data-stu-id="31589-191">Exposure score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="31589-192">Sicherheitsempfehlungen</span><span class="sxs-lookup"><span data-stu-id="31589-192">Security recommendations</span></span>](tvm-security-recommendation.md)
- [<span data-ttu-id="31589-193">Behebung von Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="31589-193">Remediate vulnerabilities</span></span>](tvm-remediation.md)
- [<span data-ttu-id="31589-194">Softwarebestand</span><span class="sxs-lookup"><span data-stu-id="31589-194">Software inventory</span></span>](tvm-software-inventory.md)


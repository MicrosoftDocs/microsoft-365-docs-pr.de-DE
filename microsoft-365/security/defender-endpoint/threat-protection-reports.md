---
title: Bedrohungsschutzbericht in Microsoft Defender for Endpoint
description: Nachverfolgen von Warnungserkennungen, Kategorien und Schweregrad mithilfe des Bedrohungsschutzberichts
keywords: Warnungserkennung, Quelle, Warnung nach Kategorie, Warnungsschweregrad, Warnungsklassifizierung, Ermittlung
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
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688981"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="71eb9-104">Bedrohungsschutzbericht in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="71eb9-104">Threat protection report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="71eb9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="71eb9-105">**Applies to:**</span></span>
- [<span data-ttu-id="71eb9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="71eb9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="71eb9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="71eb9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="71eb9-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="71eb9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="71eb9-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="71eb9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="71eb9-110">Der Bericht zum Schutz vor Bedrohungen enthält informationen auf hoher Ebene zu in Ihrer Organisation generierten Warnungen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-110">The threat protection report provides high-level information about alerts generated in your organization.</span></span> <span data-ttu-id="71eb9-111">Der Bericht enthält Trendinformationen, die die Erkennungsquellen, Kategorien, Schweregrade, Status, Klassifizierungen und Ermittlungen von Warnungen über einen bestimmten Zeitraum hinweg anzeigen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-111">The report includes trending information showing the detection sources, categories, severities, statuses, classifications, and determinations of alerts across time.</span></span>

<span data-ttu-id="71eb9-112">Das Dashboard ist in zwei Abschnitte unterteilt:</span><span class="sxs-lookup"><span data-stu-id="71eb9-112">The dashboard is structured into two sections:</span></span>

![Abbildung des Bedrohungsschutzberichts](images/threat-protection-reports.png)

<span data-ttu-id="71eb9-114">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="71eb9-114">Section</span></span> | <span data-ttu-id="71eb9-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71eb9-115">Description</span></span> 
:---|:---
<span data-ttu-id="71eb9-116">1</span><span class="sxs-lookup"><span data-stu-id="71eb9-116">1</span></span> | <span data-ttu-id="71eb9-117">Benachrichtigungstrends</span><span class="sxs-lookup"><span data-stu-id="71eb9-117">Alerts trends</span></span>
<span data-ttu-id="71eb9-118">2</span><span class="sxs-lookup"><span data-stu-id="71eb9-118">2</span></span> | <span data-ttu-id="71eb9-119">Warnungszusammenfassung</span><span class="sxs-lookup"><span data-stu-id="71eb9-119">Alert summary</span></span>

## <a name="alert-trends"></a><span data-ttu-id="71eb9-120">Warnungstrends</span><span class="sxs-lookup"><span data-stu-id="71eb9-120">Alert trends</span></span>
<span data-ttu-id="71eb9-121">Standardmäßig werden in den Warnungstrends Warnungsinformationen aus dem 30-Tage-Zeitraum angezeigt, der am letzten ganztägigen Tag endet.</span><span class="sxs-lookup"><span data-stu-id="71eb9-121">By default, the alert trends display alert information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="71eb9-122">Um eine bessere Perspektive für Trends in Ihrer Organisation zu gewinnen, können Sie den Berichtszeitraum optimieren, indem Sie den angezeigten Zeitraum anpassen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-122">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="71eb9-123">Wählen Sie einen Zeitraum aus den Dropdownoptionen aus, um den Zeitraum anzupassen:</span><span class="sxs-lookup"><span data-stu-id="71eb9-123">To adjust the time period, select a time range from the drop-down options:</span></span>

- <span data-ttu-id="71eb9-124">30 Tage</span><span class="sxs-lookup"><span data-stu-id="71eb9-124">30 days</span></span>
- <span data-ttu-id="71eb9-125">3 Monate</span><span class="sxs-lookup"><span data-stu-id="71eb9-125">3 months</span></span>
- <span data-ttu-id="71eb9-126">6 Monate</span><span class="sxs-lookup"><span data-stu-id="71eb9-126">6 months</span></span>
- <span data-ttu-id="71eb9-127">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="71eb9-127">Custom</span></span>

>[!NOTE]
><span data-ttu-id="71eb9-128">Diese Filter werden nur auf den Abschnitt Warnungstrends angewendet.</span><span class="sxs-lookup"><span data-stu-id="71eb9-128">These filters are only applied on the alert trends section.</span></span> <span data-ttu-id="71eb9-129">Der Abschnitt "Warnungszusammenfassung" hat keine Auswirkungen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-129">It doesn't affect the alert summary section.</span></span>


## <a name="alert-summary"></a><span data-ttu-id="71eb9-130">Warnungszusammenfassung</span><span class="sxs-lookup"><span data-stu-id="71eb9-130">Alert summary</span></span>
<span data-ttu-id="71eb9-131">Während die Warnungstrends trendende Warnungsinformationen zeigen, werden in der Warnungszusammenfassung Benachrichtigungsinformationen angezeigt, die auf den aktuellen Tag begrenzt sind.</span><span class="sxs-lookup"><span data-stu-id="71eb9-131">While the alert trends shows trending alert information, the alert summary shows alert information scoped to the current day.</span></span>

 <span data-ttu-id="71eb9-132">Mit der Warnungszusammenfassung können Sie einen Drilldown zu einer bestimmten Warnwarteschlange mit dem entsprechenden Filter erstellen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-132">The alert summary allows you to drill down to a particular alert queue with the corresponding filter applied to it.</span></span> <span data-ttu-id="71eb9-133">Wenn Sie beispielsweise auf die EDR auf der Karte Erkennungsquellen klicken, erhalten Sie die Benachrichtigungswarteschlange mit Ergebnissen, die nur Warnungen anzeigen, die EDR werden.</span><span class="sxs-lookup"><span data-stu-id="71eb9-133">For example, clicking on the EDR bar in the Detection sources card will bring you the alerts queue with results showing only alerts generated from EDR detections.</span></span> 

>[!NOTE]
><span data-ttu-id="71eb9-134">Die im Zusammenfassungsabschnitt angezeigten Daten sind auf 180 Tage vor dem aktuellen Datum begrenzt.</span><span class="sxs-lookup"><span data-stu-id="71eb9-134">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="71eb9-135">Wenn das heutige Datum beispielsweise der 5. November 2019 ist, werden die Daten im Zusammenfassungsabschnitt Zahlen vom 5. Mai 2019 bis zum 5. November 2019 widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="71eb9-135">For example if today's date is November 5, 2019, the data on the summary section will reflect numbers starting from May 5, 2019 to November 5, 2019.</span></span><br>
> <span data-ttu-id="71eb9-136">Der auf den Abschnitt Trends angewendete Filter wird nicht auf den Zusammenfassungsabschnitt angewendet.</span><span class="sxs-lookup"><span data-stu-id="71eb9-136">The filter applied on the trends section is not applied on the summary section.</span></span> 

## <a name="alert-attributes"></a><span data-ttu-id="71eb9-137">Warnungsattribute</span><span class="sxs-lookup"><span data-stu-id="71eb9-137">Alert attributes</span></span>
<span data-ttu-id="71eb9-138">Der Bericht besteht aus Karten, die die folgenden Warnungsattribute anzeigen:</span><span class="sxs-lookup"><span data-stu-id="71eb9-138">The report is made up of cards that display the following alert attributes:</span></span>

- <span data-ttu-id="71eb9-139">**Erkennungsquellen**: enthält Informationen zu den Sensoren und Erkennungstechnologien, die die von Microsoft Defender for Endpoint zum Auslösen von Warnungen verwendeten Daten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-139">**Detection sources**: shows information about the sensors and detection technologies that provide the data used by Microsoft Defender for Endpoint to trigger alerts.</span></span>

- <span data-ttu-id="71eb9-140">**Bedrohungskategorien**: zeigt die Arten von Bedrohungs- oder Angriffsaktivitäten an, die Warnungen ausgelöst haben, und gibt mögliche Fokusbereiche für Ihre Sicherheitsvorgänge an.</span><span class="sxs-lookup"><span data-stu-id="71eb9-140">**Threat categories**: shows the types of threat or attack activity that triggered alerts, indicating possible focus areas for your security operations.</span></span>

- <span data-ttu-id="71eb9-141">**Schweregrad**: zeigt den Schweregrad von Warnungen an, der die kollektiven potenziellen Auswirkungen von Bedrohungen für Ihre Organisation und die Reaktionsebene angibt, die für ihre Reaktion erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="71eb9-141">**Severity**: shows the severity level of alerts, indicating the collective potential impact of threats to your organization and the level of response needed to address them.</span></span>

- <span data-ttu-id="71eb9-142">**Status**: zeigt den Auflösungsstatus von Warnungen an, der die Effizienz Ihrer manuellen Warnungsantworten und der automatisierten Korrektur angibt (sofern aktiviert).</span><span class="sxs-lookup"><span data-stu-id="71eb9-142">**Status**: shows the resolution status of alerts, indicating the efficiency of your manual alert responses and of automated remediation (if enabled).</span></span> 

- <span data-ttu-id="71eb9-143">**Klassifizierung & Bestimmung**: zeigt, wie Sie Warnungen bei der Lösung klassifiziert haben, ob Sie sie als tatsächliche Bedrohungen (echte Warnungen) oder als falsche Erkennungen (falsche Warnungen) klassifiziert haben.</span><span class="sxs-lookup"><span data-stu-id="71eb9-143">**Classification & determination**: shows how you have classified alerts upon resolution, whether you have classified them as actual threats (true alerts) or as incorrect detections (false alerts).</span></span> <span data-ttu-id="71eb9-144">Diese Karten zeigen auch die Ermittlung aufgelöster Warnungen und bieten zusätzliche Einblicke, z. B. die Art der tatsächlich gefundenen Bedrohungen oder die legitimen Aktivitäten, die falsch erkannt wurden.</span><span class="sxs-lookup"><span data-stu-id="71eb9-144">These cards also show the determination of resolved alerts, providing additional insight like the types of actual threats found or the legitimate activities that were incorrectly detected.</span></span>


 

## <a name="filter-data"></a><span data-ttu-id="71eb9-145">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="71eb9-145">Filter data</span></span>

<span data-ttu-id="71eb9-146">Verwenden Sie die bereitgestellten Filter, um Warnungen mit bestimmten Attributen ein- oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="71eb9-146">Use the provided filters to include or exclude alerts with certain attributes.</span></span>

>[!NOTE]
><span data-ttu-id="71eb9-147">Diese Filter gelten **für alle** Karten im Bericht.</span><span class="sxs-lookup"><span data-stu-id="71eb9-147">These filters apply to **all** the cards in the report.</span></span>

<span data-ttu-id="71eb9-148">So zeigen Sie beispielsweise nur Daten zu Warnungen mit hohem Schweregrad an:</span><span class="sxs-lookup"><span data-stu-id="71eb9-148">For example, to show data about high-severity alerts only:</span></span>

1. <span data-ttu-id="71eb9-149">Wählen **Sie unter Filter > Schweregrad** die Option Hoch **aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb9-149">Under **Filters > Severity**, select **High**</span></span>
2. <span data-ttu-id="71eb9-150">Stellen Sie sicher, dass alle anderen Optionen unter **Schweregrad** deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="71eb9-150">Ensure that all other options under **Severity** are deselected.</span></span>
3. <span data-ttu-id="71eb9-151">Wählen Sie **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="71eb9-151">Select **Apply**.</span></span> 

## <a name="related-topic"></a><span data-ttu-id="71eb9-152">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="71eb9-152">Related topic</span></span>
- [<span data-ttu-id="71eb9-153">Bericht über Geräteintegität und -kompatibilität</span><span class="sxs-lookup"><span data-stu-id="71eb9-153">Device health and compliance report</span></span>](machine-reports.md)

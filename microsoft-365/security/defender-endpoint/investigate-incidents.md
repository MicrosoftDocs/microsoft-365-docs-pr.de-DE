---
title: Untersuchen von Vorfällen in Microsoft Defender für Endpunkt
description: Anzeigen zugehöriger Warnungen, Verwalten des Vorfalls und Anzeigen von Warnungsmetadaten, die Ihnen bei der Untersuchung eines Vorfalls helfen
keywords: untersuchen, Vorfall, Warnungen, Metadaten, Risiko, Erkennungsquelle, betroffene Geräte, Muster, Korrelation
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
ms.openlocfilehash: 0b52b6f9b457dbe1a5984c3d68c7077f7037d498
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845078"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="6771b-104">Untersuchen von Vorfällen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6771b-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6771b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6771b-105">**Applies to:**</span></span>
- [<span data-ttu-id="6771b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6771b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6771b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6771b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="6771b-108">Untersuchen Sie Vorfälle, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten, und sammeln Sie Nachweise, um sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6771b-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="6771b-109">Wenn Sie einen Vorfall untersuchen, sehen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6771b-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="6771b-110">Vorfalldetails</span><span class="sxs-lookup"><span data-stu-id="6771b-110">Incident details</span></span>
- <span data-ttu-id="6771b-111">Vorfallkommentare und -aktionen</span><span class="sxs-lookup"><span data-stu-id="6771b-111">Incident comments and actions</span></span>
- <span data-ttu-id="6771b-112">Registerkarten (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm)</span><span class="sxs-lookup"><span data-stu-id="6771b-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="6771b-113">Analysieren von Vorfalldetails</span><span class="sxs-lookup"><span data-stu-id="6771b-113">Analyze incident details</span></span> 
<span data-ttu-id="6771b-114">Klicken Sie auf einen Vorfall, um den **Vorfallbereich anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="6771b-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="6771b-115">Wählen Sie **die Seite "Vorfall öffnen"** aus, um die Vorfalldetails und zugehörige Informationen (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6771b-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Abbildung der Vorfalldetails1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="6771b-117">Warnungen</span><span class="sxs-lookup"><span data-stu-id="6771b-117">Alerts</span></span>
<span data-ttu-id="6771b-118">Sie können die Warnungen untersuchen und sehen, wie sie in einem Vorfall miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="6771b-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="6771b-119">Warnungen werden basierend auf den folgenden Gründen zu Vorfällen gruppiert:</span><span class="sxs-lookup"><span data-stu-id="6771b-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="6771b-120">Automatisierte Untersuchung – Die automatisierte Untersuchung hat die verknüpfte Warnung ausgelöst, während die ursprüngliche Warnung untersucht wurde.</span><span class="sxs-lookup"><span data-stu-id="6771b-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="6771b-121">Dateimerkmale – Die der Warnung zugeordneten Dateien weisen ähnliche Merkmale auf.</span><span class="sxs-lookup"><span data-stu-id="6771b-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="6771b-122">Manuelle Zuordnung – Ein Benutzer hat die Warnungen manuell verknüpft</span><span class="sxs-lookup"><span data-stu-id="6771b-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="6771b-123">Proximate Zeit : Die Warnungen wurden innerhalb eines bestimmten Zeitrahmens auf demselben Gerät ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="6771b-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="6771b-124">Gleiche Datei : Die mit der Warnung verbundenen Dateien sind identisch</span><span class="sxs-lookup"><span data-stu-id="6771b-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="6771b-125">Gleiche URL : Die URL, die die Warnung ausgelöst hat, ist identisch.</span><span class="sxs-lookup"><span data-stu-id="6771b-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Abbildung der Registerkarte "Warnungen" mit der Seite "Vorfalldetails" mit den Gründen, warum die Warnungen in diesem Vorfall miteinander verknüpft wurden](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="6771b-127">Sie können auch eine Warnung verwalten und Warnungsmetadaten zusammen mit anderen Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6771b-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="6771b-128">Weitere Informationen finden Sie unter [Untersuchen von Warnungen.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="6771b-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="6771b-129">Geräte</span><span class="sxs-lookup"><span data-stu-id="6771b-129">Devices</span></span>
<span data-ttu-id="6771b-130">Sie können auch die Geräte untersuchen, die Teil eines bestimmten Vorfalls sind oder mit einem bestimmten Vorfall in Zusammenhang stehen.</span><span class="sxs-lookup"><span data-stu-id="6771b-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="6771b-131">Weitere Informationen finden Sie unter [Untersuchen von Geräten.](investigate-machines.md)</span><span class="sxs-lookup"><span data-stu-id="6771b-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Abbildung der Registerkarte "Geräte" auf der Seite "Vorfalldetails"](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="6771b-133">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="6771b-133">Investigations</span></span>
<span data-ttu-id="6771b-134">Wählen Sie **"Untersuchungen" aus,** um alle automatischen Untersuchungen anzuzeigen, die vom System als Reaktion auf die Vorfallwarnungen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="6771b-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Abbildung der Registerkarte "Untersuchungen" auf der Seite "Vorfalldetails"](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="6771b-136">Durchgehen des Nachweises</span><span class="sxs-lookup"><span data-stu-id="6771b-136">Going through the evidence</span></span>
<span data-ttu-id="6771b-137">Microsoft Defender für Endpunkt untersucht automatisch alle von den Vorfällen unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Autoresponse und Informationen zu den wichtigen Dateien, Prozessen, Diensten und mehr bereit.</span><span class="sxs-lookup"><span data-stu-id="6771b-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="6771b-138">Jede der analysierten Entitäten wird als infiziert, behoben oder verdächtig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="6771b-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Abbildung der Registerkarte "Nachweise" auf der Seite "Vorfalldetails"](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="6771b-140">Visualisieren zugehöriger Cybersicherheitsbedrohungen</span><span class="sxs-lookup"><span data-stu-id="6771b-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="6771b-141">Microsoft Defender für Endpunkt aggregiert die Bedrohungsinformationen in einem Vorfall, damit Sie die Muster und Korrelationen sehen können, die von verschiedenen Datenpunkten ausgehen.</span><span class="sxs-lookup"><span data-stu-id="6771b-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="6771b-142">Sie können diese Korrelation über das Vorfalldiagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6771b-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="6771b-143">Vorfalldiagramm</span><span class="sxs-lookup"><span data-stu-id="6771b-143">Incident graph</span></span>
<span data-ttu-id="6771b-144">Der **Graph** beschreibt den Cybersicherheitsangriff.</span><span class="sxs-lookup"><span data-stu-id="6771b-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="6771b-145">Beispielsweise wird gezeigt, was der Einstiegspunkt war, welcher Indikator für Kompromittierung oder Aktivität auf welchem Gerät beobachtet wurde.</span><span class="sxs-lookup"><span data-stu-id="6771b-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="6771b-146">Etc.</span><span class="sxs-lookup"><span data-stu-id="6771b-146">etc.</span></span>

![Abbildung des Vorfalldiagramms](images/atp-incident-graph-tab.png)

<span data-ttu-id="6771b-148">Sie können auf die Kreise im Vorfalldiagramm klicken, um die Details der schädlichen Dateien, die zugehörigen Dateierkennungen, die Anzahl der Instanzen weltweit anzuzeigen, ob sie in Ihrer Organisation beobachtet wurde, falls ja, wie viele Instanzen es gab.</span><span class="sxs-lookup"><span data-stu-id="6771b-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Abbildung der Vorfalldetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="6771b-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="6771b-150">Related topics</span></span>
- [<span data-ttu-id="6771b-151">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="6771b-151">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="6771b-152">Untersuchen von Vorfällen in Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6771b-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="6771b-153">Verwalten von Microsoft Defender für Endpunkt-Vorfällen</span><span class="sxs-lookup"><span data-stu-id="6771b-153">Manage Microsoft Defender for Endpoint incidents</span></span>](/microsoft-365/security/defender-endpoint/manage-incidents)

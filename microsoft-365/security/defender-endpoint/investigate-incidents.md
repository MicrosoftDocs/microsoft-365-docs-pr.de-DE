---
title: Untersuchen von Vorfällen in Microsoft Defender for Endpoint
description: Siehe zugeordnete Warnungen, Verwalten des Vorfalls und Anzeigen von Warnungsmetadaten zur Untersuchung eines Vorfalls
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
ms.openlocfilehash: 1d8f4452273047684a30db3b18d1281f40f46378
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903298"
---
# <a name="investigate-incidents-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="42fdc-104">Untersuchen von Vorfällen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42fdc-104">Investigate incidents in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="42fdc-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="42fdc-105">**Applies to:**</span></span>
- [<span data-ttu-id="42fdc-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="42fdc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="42fdc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="42fdc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="42fdc-108">Untersuchen Sie Vorfälle, die Sich auf Ihr Netzwerk auswirken, verstehen Sie, was sie bedeuten, und ermitteln Sie Nachweise, um sie zu beheben.</span><span class="sxs-lookup"><span data-stu-id="42fdc-108">Investigate incidents that affect your network, understand what they mean, and collate evidence to resolve them.</span></span> 

<span data-ttu-id="42fdc-109">Wenn Sie einen Vorfall untersuchen, sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="42fdc-109">When you investigate an incident, you'll see:</span></span>
- <span data-ttu-id="42fdc-110">Vorfalldetails</span><span class="sxs-lookup"><span data-stu-id="42fdc-110">Incident details</span></span>
- <span data-ttu-id="42fdc-111">Vorfallkommentare und -aktionen</span><span class="sxs-lookup"><span data-stu-id="42fdc-111">Incident comments and actions</span></span>
- <span data-ttu-id="42fdc-112">Registerkarten (Warnungen, Geräte, Untersuchungen, Nachweise, Graph)</span><span class="sxs-lookup"><span data-stu-id="42fdc-112">Tabs (alerts, devices, investigations, evidence, graph)</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUV]


## <a name="analyze-incident-details"></a><span data-ttu-id="42fdc-113">Analysieren von Vorfalldetails</span><span class="sxs-lookup"><span data-stu-id="42fdc-113">Analyze incident details</span></span> 
<span data-ttu-id="42fdc-114">Klicken Sie auf einen Vorfall, um den Bereich **Vorfall anzuzeigen.**</span><span class="sxs-lookup"><span data-stu-id="42fdc-114">Click an incident to see the **Incident pane**.</span></span> <span data-ttu-id="42fdc-115">Wählen **Sie Seite Vorfall öffnen aus,** um die Vorfalldetails und zugehörige Informationen (Warnungen, Geräte, Untersuchungen, Nachweise, Diagramm) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="42fdc-115">Select **Open incident page** to see the incident details and related information (alerts, devices, investigations, evidence, graph).</span></span> 

![Abbildung der Vorfalldetails1](images/atp-incident-details.png)

### <a name="alerts"></a><span data-ttu-id="42fdc-117">Warnungen</span><span class="sxs-lookup"><span data-stu-id="42fdc-117">Alerts</span></span>
<span data-ttu-id="42fdc-118">Sie können die Warnungen untersuchen und sehen, wie sie in einem Vorfall miteinander verknüpft wurden.</span><span class="sxs-lookup"><span data-stu-id="42fdc-118">You can investigate the alerts and see how they were linked together in an incident.</span></span> <span data-ttu-id="42fdc-119">Warnungen werden basierend auf den folgenden Gründen in Vorfälle eingeteilt:</span><span class="sxs-lookup"><span data-stu-id="42fdc-119">Alerts are grouped into incidents based on the following reasons:</span></span>
- <span data-ttu-id="42fdc-120">Automatisierte Untersuchung – Die automatisierte Untersuchung löste die verknüpfte Warnung während der Untersuchung der ursprünglichen Warnung aus.</span><span class="sxs-lookup"><span data-stu-id="42fdc-120">Automated investigation - The automated investigation triggered the linked alert while investigating the original alert</span></span> 
- <span data-ttu-id="42fdc-121">Dateimerkmale : Die dateien, die der Warnung zugeordnet sind, haben ähnliche Merkmale.</span><span class="sxs-lookup"><span data-stu-id="42fdc-121">File characteristics - The files associated with the alert have similar characteristics</span></span>
- <span data-ttu-id="42fdc-122">Manuelle Zuordnung : Ein Benutzer hat die Warnungen manuell verknüpft.</span><span class="sxs-lookup"><span data-stu-id="42fdc-122">Manual association - A user manually linked the alerts</span></span>
- <span data-ttu-id="42fdc-123">Proximatzeit – Die Warnungen wurden auf dem gleichen Gerät innerhalb eines bestimmten Zeitrahmens ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="42fdc-123">Proximate time - The alerts were triggered on the same device within a certain timeframe</span></span>
- <span data-ttu-id="42fdc-124">Gleiche Datei : Die Dateien, die der Warnung zugeordnet sind, sind identisch.</span><span class="sxs-lookup"><span data-stu-id="42fdc-124">Same file - The files associated with the alert are exactly the same</span></span>
- <span data-ttu-id="42fdc-125">Gleiche URL – Die URL, die die Warnung ausgelöst hat, ist identisch.</span><span class="sxs-lookup"><span data-stu-id="42fdc-125">Same URL - The URL that triggered the alert is exactly the same</span></span>

![Abbildung der Registerkarte "Warnungen" mit der Seite "Vorfalldetails" mit den Gründen, aus denen die Warnungen in diesem Vorfall verknüpft wurden](images/atp-incidents-alerts-reason.png)

<span data-ttu-id="42fdc-127">Sie können auch eine Warnung verwalten und Benachrichtigungsmetadaten zusammen mit anderen Informationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="42fdc-127">You can also manage an alert and see alert metadata along with other information.</span></span> <span data-ttu-id="42fdc-128">Weitere Informationen finden Sie unter [Untersuchen von Warnungen](investigate-alerts.md).</span><span class="sxs-lookup"><span data-stu-id="42fdc-128">For more information, see [Investigate alerts](investigate-alerts.md).</span></span> 

### <a name="devices"></a><span data-ttu-id="42fdc-129">Geräte</span><span class="sxs-lookup"><span data-stu-id="42fdc-129">Devices</span></span>
<span data-ttu-id="42fdc-130">Sie können auch die Geräte untersuchen, die Teil oder im Zusammenhang mit einem bestimmten Vorfall sind.</span><span class="sxs-lookup"><span data-stu-id="42fdc-130">You can also investigate the devices that are part of, or related to, a given incident.</span></span> <span data-ttu-id="42fdc-131">Weitere Informationen finden Sie unter [Untersuchen von Geräten](investigate-machines.md).</span><span class="sxs-lookup"><span data-stu-id="42fdc-131">For more information, see [Investigate devices](investigate-machines.md).</span></span>

![Abbildung der Registerkarte "Geräte" auf der Seite "Details zu Vorfällen"](images/atp-incident-device-tab.png)

### <a name="investigations"></a><span data-ttu-id="42fdc-133">Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="42fdc-133">Investigations</span></span>
<span data-ttu-id="42fdc-134">Wählen **Sie Untersuchungen** aus, um alle automatischen Untersuchungen anzuzeigen, die vom System als Reaktion auf die Vorfallwarnungen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="42fdc-134">Select **Investigations** to see all the automatic investigations launched by the system in response to the incident alerts.</span></span>

![Abbildung der Registerkarte "Untersuchungen" auf der Seite "Details zu Vorfällen"](images/atp-incident-investigations-tab.png)

## <a name="going-through-the-evidence"></a><span data-ttu-id="42fdc-136">Durch die Nachweise</span><span class="sxs-lookup"><span data-stu-id="42fdc-136">Going through the evidence</span></span>
<span data-ttu-id="42fdc-137">Microsoft Defender for Endpoint untersucht automatisch alle unterstützten Ereignisse und verdächtigen Entitäten in den Warnungen und stellt Ihnen Autoresponse und Informationen zu wichtigen Dateien, Prozessen, Diensten und mehr zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="42fdc-137">Microsoft Defender for Endpoint automatically investigates all the incidents' supported events and suspicious entities in the alerts, providing you with autoresponse and information about the important files, processes, services, and more.</span></span> 

<span data-ttu-id="42fdc-138">Jede der analysierten Entitäten wird als infiziert, behoben oder verdächtig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="42fdc-138">Each of the analyzed entities will be marked as infected, remediated, or suspicious.</span></span> 

![Abbildung der Registerkarte "Nachweise" auf der Seite "Details zu Vorfällen"](images/atp-incident-evidence-tab.png)

## <a name="visualizing-associated-cybersecurity-threats"></a><span data-ttu-id="42fdc-140">Visualisieren zugeordneter Cybersicherheitsbedrohungen</span><span class="sxs-lookup"><span data-stu-id="42fdc-140">Visualizing associated cybersecurity threats</span></span> 
<span data-ttu-id="42fdc-141">Microsoft Defender for Endpoint aggregiert die Bedrohungsinformationen in einem Vorfall, sodass Sie die Muster und Korrelationen aus verschiedenen Datenpunkten sehen können.</span><span class="sxs-lookup"><span data-stu-id="42fdc-141">Microsoft Defender for Endpoint aggregates the threat information into an incident so you can see the patterns and correlations coming in from various data points.</span></span> <span data-ttu-id="42fdc-142">Sie können diese Korrelation über das Vorfalldiagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="42fdc-142">You can view such correlation through the incident graph.</span></span>

### <a name="incident-graph"></a><span data-ttu-id="42fdc-143">Vorfalldiagramm</span><span class="sxs-lookup"><span data-stu-id="42fdc-143">Incident graph</span></span>
<span data-ttu-id="42fdc-144">Das **Graph** die Geschichte des Cybersicherheitsangriffs.</span><span class="sxs-lookup"><span data-stu-id="42fdc-144">The **Graph** tells the story of the cybersecurity attack.</span></span> <span data-ttu-id="42fdc-145">Beispielsweise wird gezeigt, was der Einstiegspunkt war, welcher Indikator für Einemeindung oder Aktivität auf welchem Gerät beobachtet wurde.</span><span class="sxs-lookup"><span data-stu-id="42fdc-145">For example, it shows you what was the entry point, which indicator of compromise or activity was observed on which device.</span></span> <span data-ttu-id="42fdc-146">usw.</span><span class="sxs-lookup"><span data-stu-id="42fdc-146">etc.</span></span>

![Abbildung des Vorfalldiagramms](images/atp-incident-graph-tab.png)

<span data-ttu-id="42fdc-148">Sie können auf die Kreise im Vorfalldiagramm klicken, um die Details der schädlichen Dateien, die zugehörigen Dateierkennungen, die Anzahl der Instanzen weltweit anzuzeigen, ob sie in Ihrer Organisation beobachtet wurden, wenn ja, wie viele Instanzen.</span><span class="sxs-lookup"><span data-stu-id="42fdc-148">You can click the circles on the incident graph to view the details of the malicious files, associated file detections, how many instances have there been worldwide, whether it’s been observed in your organization, if so, how many instances.</span></span>

![Abbildung von Vorfalldetails](images/atp-incident-graph-details.png)

## <a name="related-topics"></a><span data-ttu-id="42fdc-150">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="42fdc-150">Related topics</span></span>
- [<span data-ttu-id="42fdc-151">Vorfallswarteschlange</span><span class="sxs-lookup"><span data-stu-id="42fdc-151">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="42fdc-152">Untersuchen von Vorfällen in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="42fdc-152">Investigate incidents in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-incidents)
- [<span data-ttu-id="42fdc-153">Verwalten von Microsoft Defender for Endpoint-Vorfällen</span><span class="sxs-lookup"><span data-stu-id="42fdc-153">Manage Microsoft Defender for Endpoint incidents</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-incidents)

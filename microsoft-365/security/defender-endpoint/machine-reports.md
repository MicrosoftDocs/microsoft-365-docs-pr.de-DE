---
title: Bericht über Geräteintehität und -kompatibilität in Microsoft Defender for Endpoint
description: Nachverfolgen von Erkennungen des Gerätestatus, Antivirusstatus, Betriebssystemplattform und Windows 10-Versionen mithilfe des Geräteinteitäts- und Complianceberichts
keywords: Integritätsstatus, Antivirus, Betriebssystemplattform, Windows 10-Version, Version, Integrität, Compliance, Status
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
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860291"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="7990c-104">Bericht über Geräteintehität und -kompatibilität in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="7990c-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7990c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7990c-105">**Applies to:**</span></span>
- [<span data-ttu-id="7990c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="7990c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7990c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7990c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="7990c-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="7990c-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7990c-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="7990c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7990c-110">Der Gerätestatusbericht enthält informationen auf hoher Ebene zu den Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7990c-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="7990c-111">Der Bericht enthält Trendinformationen, die den Sensorstatus, den Antivirusstatus, Betriebssystemplattformen und Windows 10-Versionen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7990c-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="7990c-112">Das Dashboard ist in zwei Abschnitte unterteilt: ![ Abbildung des Geräteberichts](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="7990c-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="7990c-113">Abschnitt</span><span class="sxs-lookup"><span data-stu-id="7990c-113">Section</span></span> | <span data-ttu-id="7990c-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7990c-114">Description</span></span>
:---|:---
<span data-ttu-id="7990c-115">1</span><span class="sxs-lookup"><span data-stu-id="7990c-115">1</span></span> | <span data-ttu-id="7990c-116">Gerätetrends</span><span class="sxs-lookup"><span data-stu-id="7990c-116">Device trends</span></span>
<span data-ttu-id="7990c-117">2</span><span class="sxs-lookup"><span data-stu-id="7990c-117">2</span></span> | <span data-ttu-id="7990c-118">Gerätezusammenfassung (aktueller Tag)</span><span class="sxs-lookup"><span data-stu-id="7990c-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="7990c-119">Gerätetrends</span><span class="sxs-lookup"><span data-stu-id="7990c-119">Device trends</span></span> 
<span data-ttu-id="7990c-120">Standardmäßig zeigt der Gerätetrend Geräteinformationen aus dem 30-Tage-Zeitraum an, der am letzten ganztägigen Tag endet.</span><span class="sxs-lookup"><span data-stu-id="7990c-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="7990c-121">Um eine bessere Perspektive für Trends in Ihrer Organisation zu gewinnen, können Sie den Berichtszeitraum optimieren, indem Sie den angezeigten Zeitraum anpassen.</span><span class="sxs-lookup"><span data-stu-id="7990c-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="7990c-122">Wählen Sie einen Zeitraum aus den Dropdownoptionen aus, um den Zeitraum anzupassen:</span><span class="sxs-lookup"><span data-stu-id="7990c-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="7990c-123">30 Tage</span><span class="sxs-lookup"><span data-stu-id="7990c-123">30 days</span></span>
- <span data-ttu-id="7990c-124">3 Monate</span><span class="sxs-lookup"><span data-stu-id="7990c-124">3 months</span></span>
- <span data-ttu-id="7990c-125">6 Monate</span><span class="sxs-lookup"><span data-stu-id="7990c-125">6 months</span></span>
- <span data-ttu-id="7990c-126">Benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="7990c-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="7990c-127">Diese Filter werden nur auf den Abschnitt Gerätetrends angewendet.</span><span class="sxs-lookup"><span data-stu-id="7990c-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="7990c-128">Dies wirkt sich nicht auf den Abschnitt "Gerätezusammenfassung" aus.</span><span class="sxs-lookup"><span data-stu-id="7990c-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="7990c-129">Gerätezusammenfassung</span><span class="sxs-lookup"><span data-stu-id="7990c-129">Device summary</span></span> 
<span data-ttu-id="7990c-130">Während die Gerätetrends trendende Geräteinformationen zeigen, werden in der Gerätezusammenfassung Geräteinformationen angezeigt, die auf den aktuellen Tag begrenzt sind.</span><span class="sxs-lookup"><span data-stu-id="7990c-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="7990c-131">Die im Zusammenfassungsabschnitt angezeigten Daten sind auf 180 Tage vor dem aktuellen Datum begrenzt.</span><span class="sxs-lookup"><span data-stu-id="7990c-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="7990c-132">Wenn das heutige Datum z. B. der 27. März 2019 ist, spiegeln die Daten im Zusammenfassungsabschnitt Zahlen vom 28. September 2018 bis zum 27. März 2019 wider.</span><span class="sxs-lookup"><span data-stu-id="7990c-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="7990c-133">Der auf den Abschnitt Trends angewendete Filter wird nicht auf den Zusammenfassungsabschnitt angewendet.</span><span class="sxs-lookup"><span data-stu-id="7990c-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="7990c-134">Im Abschnitt Gerätetrends können Sie einen Drilldown zur Geräteliste mit dem entsprechenden Filter erstellen.</span><span class="sxs-lookup"><span data-stu-id="7990c-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="7990c-135">Wenn Sie beispielsweise auf die Inaktive Leiste auf der Sensorstatuskarte klicken, erhalten Sie die Geräteliste mit Ergebnissen, die nur Geräte anzeigen, deren Sensorstatus inaktiv ist.</span><span class="sxs-lookup"><span data-stu-id="7990c-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="7990c-136">Geräteattribute</span><span class="sxs-lookup"><span data-stu-id="7990c-136">Device attributes</span></span>
<span data-ttu-id="7990c-137">Der Bericht besteht aus Karten, die die folgenden Geräteattribute anzeigen:</span><span class="sxs-lookup"><span data-stu-id="7990c-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="7990c-138">**Integritätsstatus:** Zeigt Informationen zum Sensorstatus auf Geräten an, die eine aggregierte Ansicht von aktiven Geräten, beeinträchtigter Kommunikation, inaktiver Oder ohne Sensordaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7990c-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="7990c-139">**Antivirusstatus für aktive Windows 10-Geräte:** zeigt die Anzahl der Geräte und den Status von Microsoft Defender Antivirus an.</span><span class="sxs-lookup"><span data-stu-id="7990c-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="7990c-140">**Betriebssystemplattformen**: zeigt die Verteilung von Betriebssystemplattformen an, die in Ihrer Organisation vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7990c-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="7990c-141">**Windows 10-Versionen**: zeigt die Verteilung von Windows 10-Geräten und deren Versionen in Ihrer Organisation an.</span><span class="sxs-lookup"><span data-stu-id="7990c-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="7990c-142">Filtern von Daten</span><span class="sxs-lookup"><span data-stu-id="7990c-142">Filter data</span></span>
 
<span data-ttu-id="7990c-143">Verwenden Sie die bereitgestellten Filter, um Geräte mit bestimmten Attributen ein- oder auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="7990c-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="7990c-144">Sie können mehrere Filter auswählen, die aus den Geräteattributen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7990c-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="7990c-145">Diese Filter gelten **für alle** Karten im Bericht.</span><span class="sxs-lookup"><span data-stu-id="7990c-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="7990c-146">So zeigen Sie z. B. Daten zu Windows 10-Geräten mit active sensor health state an:</span><span class="sxs-lookup"><span data-stu-id="7990c-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="7990c-147">Unter **Filters > Sensor health state > Active**.</span><span class="sxs-lookup"><span data-stu-id="7990c-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="7990c-148">Wählen Sie dann **Betriebssystemplattformen > Windows 10 aus.**</span><span class="sxs-lookup"><span data-stu-id="7990c-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="7990c-149">Wählen Sie **Anwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="7990c-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="7990c-150">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="7990c-150">Related topic</span></span>
- [<span data-ttu-id="7990c-151">Bedrohungsschutzbericht</span><span class="sxs-lookup"><span data-stu-id="7990c-151">Threat protection report</span></span>](threat-protection-reports.md)

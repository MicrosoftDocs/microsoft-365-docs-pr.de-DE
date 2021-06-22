---
title: Übersicht über die Geräteermittlung
description: Erfahren Sie, wie Sie die Endpunktermittlung in Microsoft 365 Defender nutzen, um nicht verwaltete Geräte in Ihrem Netzwerk zu finden.
keywords: Geräteermittlung, entdecken, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 16baaa6fd9865140d42c0ca3a566427f761a28c2
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53062214"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="68138-104">Übersicht über die Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="68138-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="68138-105">**Applies to:**</span></span>
- [<span data-ttu-id="68138-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="68138-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="68138-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68138-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


<span data-ttu-id="68138-108">Der Schutz Ihrer Umgebung erfordert eine Bestandsaufnahme der Geräte, die sich in Ihrem Netzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="68138-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="68138-109">Die Zuordnung von Geräten in einem Netzwerk kann jedoch häufig teuer, schwierig und zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="68138-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="68138-110">Microsoft Defender für Endpunkt bietet eine Geräteermittlungsfunktion, mit der Sie nicht verwaltete Geräte finden können, die mit Ihrem Unternehmensnetzwerk verbunden sind, ohne dass zusätzliche Appliances oder umständliche Prozessänderungen erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="68138-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="68138-111">Die Geräteermittlungsfunktion ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="68138-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="68138-112">**Ermitteln von Unternehmensendpunkten, die mit Ihrem Unternehmensnetzwerk verbunden sind**</span><span class="sxs-lookup"><span data-stu-id="68138-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="68138-113">Mit einfachen oder standardmäßigen Ermittlungsoptionen können Sie Arbeitsstationen, Server und mobile Endpunkte ermitteln, die noch nicht in Microsoft Defender für Endpunkt integriert sind.</span><span class="sxs-lookup"><span data-stu-id="68138-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="68138-114">**Onboarding von ermittelten Endpunkten**</span><span class="sxs-lookup"><span data-stu-id="68138-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="68138-115">Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="68138-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="68138-116">Durch das Onboarding in den Dienst kann die Sichtbarkeit der Sicherheit für sie erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="68138-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="68138-117">In Verbindung mit dieser Funktion wird eine neue Sicherheitsempfehlung zum Onboarding von Geräten in Microsoft Defender für Endpunkt als Teil der vorhandenen Bedrohungs- und Sicherheitsrisikoverwaltung verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="68138-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="68138-118">Ermittlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="68138-118">Discovery methods</span></span>
<span data-ttu-id="68138-119">Es gibt zwei Erkennungsmodi:</span><span class="sxs-lookup"><span data-stu-id="68138-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="68138-120">Grundlegende Ermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-120">Basic discovery</span></span> 
-   <span data-ttu-id="68138-121">Standardermittlung (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="68138-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="68138-122">Die Ermittlung ist auf den Basismodus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="68138-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="68138-123">Sie können diese Konfiguration über die Einstellungsseite beibehalten.</span><span class="sxs-lookup"><span data-stu-id="68138-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="68138-124">Die Standardermittlung ist der Standardmodus für alle Kunden ab dem 19. Juli 2021 , es sei denn, sie wird über die Einstellungsseite vor diesem Datum geändert.</span><span class="sxs-lookup"><span data-stu-id="68138-124">Standard discovery will be the default mode for all customers starting July 19, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="68138-125">Grundlegende Ermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-125">Basic discovery</span></span> 

<span data-ttu-id="68138-126">In diesem Modus erfassen Endpunkte passiv Ereignisse in Ihrem Netzwerk und extrahieren Geräteinformationen daraus.</span><span class="sxs-lookup"><span data-stu-id="68138-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="68138-127">Die grundlegende Ermittlung verwendet die SenseNDR.exe Binärdatei für die passive Netzwerkdatensammlung, und es wird kein Netzwerkdatenverkehr initiiert.</span><span class="sxs-lookup"><span data-stu-id="68138-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="68138-128">Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="68138-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="68138-129">Standardermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-129">Standard discovery</span></span> 

<span data-ttu-id="68138-130">Dieser Modus ermöglicht Es Endpunkten, beobachtete Geräte im Netzwerk aktiv zu untersuchen, um gesammelte Daten zu erweitern, sodass Sie einen zuverlässigen und konsistenten Gerätebestand erstellen können.</span><span class="sxs-lookup"><span data-stu-id="68138-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="68138-131">Der Standardmodus verwendet intelligente, aktive Untersuchung, um noch mehr Informationen zu beobachteten Geräten zu ermitteln, um vorhandene Geräteinformationen zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="68138-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="68138-132">Wenn der Standardmodus aktiviert ist, werden minimale und geringfügige Netzwerkaktivitäten, die vom Ermittlungssensor generiert werden, möglicherweise von Netzwerküberwachungstools in Ihrer Organisation beobachtet.</span><span class="sxs-lookup"><span data-stu-id="68138-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="68138-133">Wenn Sie diesen Modus nicht aktivieren, erhalten Sie nur eingeschränkte Sichtbarkeit von nicht verwalteten Endpunkten in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="68138-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="68138-134">Standard Discovery verwendet verschiedene PowerShell-Skripts, um Geräte im Netzwerk aktiv zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="68138-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="68138-135">Diese PowerShell-Skripts sind von Microsoft signiert und werden an folgendem Speicherort ausgeführt: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` .</span><span class="sxs-lookup"><span data-stu-id="68138-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="68138-136">Beispiel: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span><span class="sxs-lookup"><span data-stu-id="68138-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="68138-137">Sie können Ihre Ermittlungseinstellungen ändern und anpassen. Weitere Informationen finden Sie unter [Konfigurieren der Geräteermittlung.](configure-device-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="68138-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="68138-138">Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="68138-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="68138-139">Geräte, die nicht mit Unternehmensnetzwerken verbunden sind, werden nicht ermittelt oder im Gerätebestand aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="68138-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="68138-140">Gerätebestand</span><span class="sxs-lookup"><span data-stu-id="68138-140">Device Inventory</span></span> 
<span data-ttu-id="68138-141">Geräte, die ermittelt wurden, aber noch nicht integriert und von Microsoft Defender für Endpunkt gesichert wurden, werden im Geräteinventar auf der Registerkarte "Endpunkte" aufgeführt. Sie können nun einen neuen Filter in der Gerätebestandsliste namens Onboardingstatus verwenden, der einen der folgenden Werte aufweisen kann:</span><span class="sxs-lookup"><span data-stu-id="68138-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="68138-142">Onboarded – Der Endpunkt ist in Microsoft Defender für Endpunkt integriert.</span><span class="sxs-lookup"><span data-stu-id="68138-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="68138-143">Kann integriert werden – Der Endpunkt wurde im Netzwerk ermittelt, und das Betriebssystem wurde als ein Endpunkt identifiziert, der von Microsoft Defender für Endpunkt unterstützt wird, aber derzeit nicht integriert ist.</span><span class="sxs-lookup"><span data-stu-id="68138-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="68138-144">Es wird dringend empfohlen, diese Geräte zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="68138-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="68138-145">Nicht unterstützt – Der Endpunkt wurde im Netzwerk ermittelt, wird jedoch von Microsoft Defender für Endpunkt nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="68138-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="68138-146">Unzureichende Informationen – Das System konnte die Unterstützung des Geräts nicht ermitteln.</span><span class="sxs-lookup"><span data-stu-id="68138-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="68138-147">Das Aktivieren der Standardermittlung auf mehr Geräten im Netzwerk kann die ermittelten Attribute erweitern.</span><span class="sxs-lookup"><span data-stu-id="68138-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![Abbildung des Geräteinventar-Dashboards](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> <span data-ttu-id="68138-149">Sie können immer Filter anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="68138-149">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="68138-150">Sie können auch die Spalte "Onboardingstatus" in API-Abfragen verwenden, um nicht verwaltete Geräte herauszufiltern.</span><span class="sxs-lookup"><span data-stu-id="68138-150">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="68138-151">Bewertung von Sicherheitsrisiken auf ermittelten Geräten</span><span class="sxs-lookup"><span data-stu-id="68138-151">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="68138-152">Sicherheitsrisiken und Risiken auf Ihren Geräten sowie andere ermittelte nicht verwaltete Geräte im Netzwerk sind Teil des aktuellen TVM-Flusses unter "Sicherheit Empfehlungen" und werden auf Entitätsseiten im portalweiten Bereich dargestellt.</span><span class="sxs-lookup"><span data-stu-id="68138-152">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="68138-153">Suchen Sie nach "SSH"-Sicherheitsempfehlungen, um SSH-Sicherheitsrisiken zu finden, die mit nicht verwalteten und verwalteten Geräten zusammenhängen.</span><span class="sxs-lookup"><span data-stu-id="68138-153">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![Abbildung des Dashboards für Sicherheitsempfehlungen](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="68138-155">Verwenden der erweiterten Suche auf ermittelten Geräten</span><span class="sxs-lookup"><span data-stu-id="68138-155">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="68138-156">Sie können Abfragen der erweiterten Suche verwenden, um Aufschlüsse auf ermittelten Geräten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="68138-156">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="68138-157">Hier finden Sie Details zu ermittelten Endpunkten in der DeviceInfo-Tabelle oder netzwerkbezogene Informationen zu diesen Geräten in der DeviceNetworkInfo-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="68138-157">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![Abbildung der verwendung der erweiterten Suche](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="68138-159">Die Gerätesuche nutzt integrierte Geräte von Microsoft Defender für Endpunkt als Netzwerkdatenquelle, um Aktivitäten nicht integrierten Geräten zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="68138-159">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="68138-160">Dies bedeutet, dass, wenn ein integriertes Microsoft Defender für Endpunkt-Gerät mit einem nicht integrierten Gerät kommuniziert, Aktivitäten auf dem nicht integrierten Gerät auf der Zeitachse und über die DeviceNetworkEvents-Tabelle für die erweiterte Suche angezeigt werden können.</span><span class="sxs-lookup"><span data-stu-id="68138-160">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="68138-161">Neue Ereignisse sind TCP-Verbindungen (Transmission Control Protocol) und passen in das aktuelle DeviceNetworkEvents-Schema.</span><span class="sxs-lookup"><span data-stu-id="68138-161">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="68138-162">TCP-Ausgang an das Microsoft Defender für Endpunkt-aktivierte Gerät von einem nicht von Microsoft Defender für Endpunkt aktivierten Gerät.</span><span class="sxs-lookup"><span data-stu-id="68138-162">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="68138-163">Die folgenden Aktionstypen wurden ebenfalls hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="68138-163">The following action types have also been added:</span></span>  

- <span data-ttu-id="68138-164">ConnectionAttempt – Ein Versuch, eine TCP-Verbindung herzustellen (syn)</span><span class="sxs-lookup"><span data-stu-id="68138-164">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="68138-165">ConnectionAcknowledged – Eine Bestätigung, dass eine TCP-Verbindung akzeptiert wurde (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="68138-165">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="68138-166">Sie können diese Beispielabfrage testen:</span><span class="sxs-lookup"><span data-stu-id="68138-166">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a><span data-ttu-id="68138-167">Geändertes Verhalten</span><span class="sxs-lookup"><span data-stu-id="68138-167">Changed behavior</span></span>
<span data-ttu-id="68138-168">Im folgenden Abschnitt sind die Änderungen aufgeführt, die Sie in Microsoft Defender für Endpunkt und/oder Microsoft 365 Security Center beobachten werden, wenn diese Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68138-168">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="68138-169">Geräte, die nicht in Microsoft Defender zu Endpunkt integriert sind, werden voraussichtlich im Gerätebestand, in der erweiterten Suche und in API-Abfragen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="68138-169">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="68138-170">Dies kann die Größe der Abfrageergebnisse erheblich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="68138-170">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="68138-171">Die Tabellen "DeviceInfo" und "DeviceNetworkInfo" in der erweiterten Suche enthalten nun das ermittelte Gerät.</span><span class="sxs-lookup"><span data-stu-id="68138-171">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="68138-172">Sie können diese Geräte mithilfe des "OnboardingStatus"-Attributs herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="68138-172">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="68138-173">Es wird erwartet, dass ermittelte Geräte in den Abfrageergebnissen der Streaming-API angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="68138-173">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="68138-174">Sie können diese Geräte herausfiltern, indem Sie den `OnboardingStatus` Filter in Ihrer Abfrage verwenden.</span><span class="sxs-lookup"><span data-stu-id="68138-174">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="68138-175">Nicht verwaltete Geräte werden vorhandenen Gerätegruppen basierend auf den definierten Kriterien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="68138-175">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="68138-176">In seltenen Fällen kann die Standardermittlung Warnungen auf Netzwerkmonitoren oder Sicherheitstools auslösen.</span><span class="sxs-lookup"><span data-stu-id="68138-176">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="68138-177">Bitte geben Sie Feedback, wenn Sie solche Ereignisse erleben, um zu verhindern, dass sich diese Probleme wiederholen.</span><span class="sxs-lookup"><span data-stu-id="68138-177">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="68138-178">Sie können explizit ausschließen, dass bestimmte Ziele oder ganze Subnetze von der Standardermittlung aktiv untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="68138-178">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="68138-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="68138-179">Next steps</span></span>
- [<span data-ttu-id="68138-180">Konfigurieren der Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-180">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="68138-181">Häufig gestellte Fragen zur Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="68138-181">Device discovery FAQs</span></span>](device-discovery-faq.md)

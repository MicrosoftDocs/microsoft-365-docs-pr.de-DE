---
title: Übersicht über die Geräteermittlung
description: Erfahren Sie, wie Sie die Endpunkterkennung in Microsoft 365 Defender nutzen, um nicht verwaltete Geräte in Ihrem Netzwerk zu finden.
keywords: Geräteerkennung, Ermittlung, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
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
ms.openlocfilehash: 2dee1193e9f852e66df324927bf38d37d736d251
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245948"
---
# <a name="device-discovery-overview"></a><span data-ttu-id="e66b9-104">Übersicht über die Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="e66b9-104">Device discovery overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e66b9-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="e66b9-105">**Applies to:**</span></span>
- [<span data-ttu-id="e66b9-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="e66b9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="e66b9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e66b9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="e66b9-108">Zum Schutz Ihrer Umgebung müssen Sie eine Bestandsaufnahme der Geräte in Ihrem Netzwerk verwenden.</span><span class="sxs-lookup"><span data-stu-id="e66b9-108">Protecting your environment requires taking inventory of the devices that are in your network.</span></span> <span data-ttu-id="e66b9-109">Die Zuordnung von Geräten in einem Netzwerk kann jedoch häufig kostspielig, schwierig und zeitaufwändig sein.</span><span class="sxs-lookup"><span data-stu-id="e66b9-109">However, mapping devices in a network can often be expensive, challenging, and time-consuming.</span></span> 

<span data-ttu-id="e66b9-110">Microsoft Defender for Endpoint bietet eine Geräteerkennungsfunktion, mit der Sie nicht verwaltete Geräte finden können, die mit Ihrem Unternehmensnetzwerk verbunden sind, ohne dass zusätzliche Appliances oder aufwändige Prozessänderungen nötig sind.</span><span class="sxs-lookup"><span data-stu-id="e66b9-110">Microsoft Defender for Endpoint provides a device discovery capability that helps you find unmanaged devices connected to your corporate network without the need for extra appliances or cumbersome process changes.</span></span>


<span data-ttu-id="e66b9-111">Mit der Geräteerkennungsfunktion können Sie:</span><span class="sxs-lookup"><span data-stu-id="e66b9-111">The device discovery capability allows you to:</span></span>

- <span data-ttu-id="e66b9-112">**Ermitteln von Unternehmensendpunkten, die mit Ihrem Unternehmensnetzwerk verbunden sind**</span><span class="sxs-lookup"><span data-stu-id="e66b9-112">**Discover enterprise endpoints connected to your corporate network**</span></span> <br>
<span data-ttu-id="e66b9-113">Mithilfe von einfachen oder standardmäßigen Ermittlungsoptionen können Sie Arbeitsstationen, Server und mobile Endpunkte ermitteln, die noch nicht in Microsoft Defender for Endpoint integrierte sind.</span><span class="sxs-lookup"><span data-stu-id="e66b9-113">Using either basic or standard discovery options, you can discover workstations, servers, and mobile endpoints that are not yet onboarded to Microsoft Defender for Endpoint.</span></span>  

- <span data-ttu-id="e66b9-114">**Onboarding von ermittelten Endpunkten**</span><span class="sxs-lookup"><span data-stu-id="e66b9-114">**Onboard discovered endpoints**</span></span><br>
<span data-ttu-id="e66b9-115">Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e66b9-115">Unmanaged endpoints in your network introduce vulnerabilities and risks to your network.</span></span> <span data-ttu-id="e66b9-116">Das Onboarding in den Dienst kann die Sichtbarkeit der Dienste erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-116">Onboarding them to the service can increase the security visibility on them.</span></span> 

<span data-ttu-id="e66b9-117">In Verbindung mit dieser Funktion wird eine neue Sicherheitsempfehlung zum Onboarding von Geräten in Microsoft Defender for Endpoint im Rahmen der vorhandenen Bedrohungs- und Sicherheitsrisikoverwaltung verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="e66b9-117">In conjunction with this capability, a new security recommendation to onboard devices to Microsoft Defender for Endpoint will be available as part of the existing Threat and Vulnerability Management experience.</span></span>



## <a name="discovery-methods"></a><span data-ttu-id="e66b9-118">Ermittlungsmethoden</span><span class="sxs-lookup"><span data-stu-id="e66b9-118">Discovery methods</span></span>
<span data-ttu-id="e66b9-119">Es gibt zwei Erkennungsmodi:</span><span class="sxs-lookup"><span data-stu-id="e66b9-119">There are two modes of discovery:</span></span> 

-   <span data-ttu-id="e66b9-120">Grundlegende Ermittlung</span><span class="sxs-lookup"><span data-stu-id="e66b9-120">Basic discovery</span></span> 
-   <span data-ttu-id="e66b9-121">Standardermittlung (empfohlen)</span><span class="sxs-lookup"><span data-stu-id="e66b9-121">Standard discovery (recommended)</span></span> 


> [!IMPORTANT]
> <span data-ttu-id="e66b9-122">Die Ermittlung ist auf den Basismodus festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-122">Discovery is set to basic mode.</span></span> <span data-ttu-id="e66b9-123">Sie können diese Konfiguration über die Einstellungsseite beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e66b9-123">You can choose to retain this configuration through the settings page.</span></span> <span data-ttu-id="e66b9-124">Die Standardermittlung ist der Standardmodus für alle Vorschaukunden ab dem 10. Mai 2021 , sofern sie nicht vor diesem Datum über die Einstellungsseite geändert wird.</span><span class="sxs-lookup"><span data-stu-id="e66b9-124">Standard discovery will be the default mode for all preview customers starting May 10, 2021 - unless modified through the settings page before this date.</span></span>

### <a name="basic-discovery"></a><span data-ttu-id="e66b9-125">Grundlegende Ermittlung</span><span class="sxs-lookup"><span data-stu-id="e66b9-125">Basic discovery</span></span> 

<span data-ttu-id="e66b9-126">In diesem Modus erfassen Endpunkte passiv Ereignisse in Ihrem Netzwerk und extrahieren Geräteinformationen aus ihnen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-126">In this mode, endpoints will passively collect events in your network and extract device information from them.</span></span> <span data-ttu-id="e66b9-127">Die grundlegende Ermittlung verwendet die SenseNDR.exe für die passive Netzwerkdatenerfassung, und es wird kein Netzwerkdatenverkehr initiiert.</span><span class="sxs-lookup"><span data-stu-id="e66b9-127">Basic discovery uses the SenseNDR.exe binary for passive network data collection and no network traffic will be initiated.</span></span> <span data-ttu-id="e66b9-128">Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e66b9-128">Endpoints will simply extract data from every network traffic that is seen by an onboarded device.</span></span> 

### <a name="standard-discovery"></a><span data-ttu-id="e66b9-129">Standardermittlung</span><span class="sxs-lookup"><span data-stu-id="e66b9-129">Standard discovery</span></span> 

<span data-ttu-id="e66b9-130">Mit diesem Modus können Endpunkte beobachtete Geräte im Netzwerk aktiv austesten, um die gesammelten Daten zu bereichern und so eine zuverlässige und zusammenhängende Geräteinventarisierung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-130">This mode allows endpoints to actively probe observed devices in the network to enrich collected data - helping you build a reliable and coherent device inventory.</span></span> <span data-ttu-id="e66b9-131">Der Standardmodus verwendet intelligentes, aktives Sondieren, um noch mehr Informationen zu beobachteten Geräten zu ermitteln, um vorhandene Geräteinformationen zu bereichern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-131">Standard mode uses smart, active probing to discover even more information about observed devices to enrich existing device information.</span></span>  

<span data-ttu-id="e66b9-132">Wenn der Standardmodus aktiviert ist, werden minimale und vernachlässigbare Netzwerkaktivitäten, die vom Ermittlungssensor generiert werden, möglicherweise von Den Netzwerküberwachungstools in Ihrer Organisation beobachtet.</span><span class="sxs-lookup"><span data-stu-id="e66b9-132">When Standard mode is enabled, minimal and negligible network activity generated by the discovery sensor might be observed by network monitoring tools in your organization.</span></span>  

 <span data-ttu-id="e66b9-133">Wenn Sie diesen Modus nicht aktivieren möchten, erhalten Sie nur eingeschränkte Sichtbarkeit nicht verwalteter Endpunkte in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="e66b9-133">If you choose not to enable this mode, you will only gain limited visibility of unmanaged endpoints in your network.</span></span>

<span data-ttu-id="e66b9-134">Die Standardermittlung verwendet verschiedene PowerShell-Skripts, um Geräte im Netzwerk aktiv zu testen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-134">Standard discovery uses various PowerShell scripts to actively probe devices in the network.</span></span> <span data-ttu-id="e66b9-135">Diese PowerShell-Skripts sind von Microsoft signiert und werden an folgendem Speicherort ausgeführt: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` .</span><span class="sxs-lookup"><span data-stu-id="e66b9-135">Those PowerShell scripts are Microsoft signed and are executed from the following location: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`.</span></span> <span data-ttu-id="e66b9-136">Beispiel: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span><span class="sxs-lookup"><span data-stu-id="e66b9-136">For example, `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.</span></span>

<span data-ttu-id="e66b9-137">Sie können Ihre Discoveryeinstellungen ändern und anpassen, weitere Informationen finden Sie unter [Configure device discovery](configure-device-discovery.md).</span><span class="sxs-lookup"><span data-stu-id="e66b9-137">You can change and customize your discovery settings, for more information see [Configure device discovery](configure-device-discovery.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e66b9-138">Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks.</span><span class="sxs-lookup"><span data-stu-id="e66b9-138">The discovery engine distinguishes between network events that are received in the corporate network versus outside of the corporate network.</span></span> <span data-ttu-id="e66b9-139">Geräte, die nicht mit Unternehmensnetzwerken verbunden sind, werden nicht ermittelt oder im Gerätebestand aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-139">Devices that are not connected to corporate networks will not be discovered or listed in the device inventory.</span></span> 



## <a name="device-inventory"></a><span data-ttu-id="e66b9-140">Gerätebestand</span><span class="sxs-lookup"><span data-stu-id="e66b9-140">Device Inventory</span></span> 
<span data-ttu-id="e66b9-141">Geräte, die entdeckt wurden, aber noch nicht von Microsoft Defender for Endpoint onboarded und gesichert wurden, werden auf der Registerkarte Endpunkte unter Geräteinventar aufgeführt. Sie können jetzt einen neuen Filter in der Geräteinventarliste namens Onboarding-Status verwenden, der einen der folgenden Werte haben kann:</span><span class="sxs-lookup"><span data-stu-id="e66b9-141">Devices that have been discovered but have not yet been onboarded and secured by Microsoft Defender for Endpoint will be listed in Device Inventory within the Endpoints tab. You can now use a new filter in the device inventory list called Onboarding status which can have any of the following values:</span></span>

- <span data-ttu-id="e66b9-142">Onboarded – Der Endpunkt wird in Microsoft Defender for Endpoint onboarded.</span><span class="sxs-lookup"><span data-stu-id="e66b9-142">Onboarded – The endpoint is onboarded to Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="e66b9-143">Kann onboarded werden– Der Endpunkt wurde im Netzwerk erkannt, und das Betriebssystem wurde als ein Endpunkt identifiziert, der von Microsoft Defender for Endpoint unterstützt wird, aber derzeit nicht onboarded ist.</span><span class="sxs-lookup"><span data-stu-id="e66b9-143">Can be onboarded – The endpoint was discovered in the network and the Operating System was identified as one that is supported by Microsoft Defender for Endpoint, but it is not currently onboarded.</span></span> <span data-ttu-id="e66b9-144">Es wird dringend empfohlen, diese Geräte zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="e66b9-144">We highly recommend onboarding these devices.</span></span>
- <span data-ttu-id="e66b9-145">Nicht unterstützt – Der Endpunkt wurde im Netzwerk ermittelt, wird jedoch nicht von Microsoft Defender for Endpoint unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-145">Unsupported – The endpoint was discovered in the network but is not supported by Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="e66b9-146">Unzureichende Informationen – Das System konnte die Unterstützungsfähigkeit des Geräts nicht ermitteln.</span><span class="sxs-lookup"><span data-stu-id="e66b9-146">Insufficient info – The system could not determine the supportability of the device.</span></span> <span data-ttu-id="e66b9-147">Das Aktivieren der Standarderkennung auf mehr Geräten im Netzwerk kann die ermittelten Attribute bereichern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-147">Enabling standard discovery on more devices in the network can enrich the discovered attributes.</span></span> 
 

![Abbildung des Geräteinventardashboards](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> <span data-ttu-id="e66b9-149">Sie können filter immer anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-149">You can always apply filters to exclude unmanaged devices from the device inventory list.</span></span> <span data-ttu-id="e66b9-150">Sie können auch die Spalte Onboardingstatus in API-Abfragen verwenden, um nicht verwaltete Geräte herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-150">You can also use the onboarding status column on API queries to filter out unmanaged devices.</span></span> 

## <a name="vulnerability-assessment-on-discovered-devices"></a><span data-ttu-id="e66b9-151">Sicherheitsrisikobewertung auf erkannten Geräten</span><span class="sxs-lookup"><span data-stu-id="e66b9-151">Vulnerability assessment on discovered devices</span></span>
<span data-ttu-id="e66b9-152">Sicherheitsrisiken und Risiken auf Ihren Geräten sowie andere ermittelte nicht verwaltete Geräte im Netzwerk sind Teil der aktuellen TVM-Flüsse unter "Security Empfehlungen" und werden auf Entitätsseiten im gesamten Portal dargestellt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-152">Vulnerabilities and risks on your devices as well as other discovered unmanaged devices in the network are part of the current TVM flows under "Security Recommendations" and represented in entity pages across the portal.</span></span> <span data-ttu-id="e66b9-153">Suchen Sie nach "SSH"-bezogenen Sicherheitsempfehlungen, um SSH-Sicherheitsrisiken zu finden, die für nicht verwaltete und verwaltete Geräte im Zusammenhang stehen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-153">Search for "SSH" related security recommendations to find SSH vulnerabilities that are related for unmanaged and managed devices.</span></span> 

![Abbildung des Dashboards für Sicherheitsempfehlungen](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a><span data-ttu-id="e66b9-155">Verwenden der erweiterten Suche auf erkannten Geräten</span><span class="sxs-lookup"><span data-stu-id="e66b9-155">Use Advanced Hunting on discovered devices</span></span>
<span data-ttu-id="e66b9-156">Sie können erweiterte Suchabfragen verwenden, um die Sichtbarkeit auf ermittelten Geräten zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-156">You can use Advanced Hunting queries to gain visibility on discovered devices.</span></span>
<span data-ttu-id="e66b9-157">In der Tabelle DeviceInfo finden Sie Details zu ermittelten Endpunkten oder netzwerkbezogene Informationen zu diesen Geräten in der DeviceNetworkInfo-Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e66b9-157">Find details about discovered Endpoints in the DeviceInfo table, or network-related information about those devices in the DeviceNetworkInfo table.</span></span>
  

![Abbildung der erweiterten Verwendung der Suche](images/f48ba1779eddee9872f167453c24e5c9.png)


<span data-ttu-id="e66b9-159">Die Geräteerkennung nutzt integrierte Microsoft Defender for Endpoint-Geräte als Netzwerkdatenquelle, um Aktivitäten nicht integrierten Geräten zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-159">Device discovery leverages Microsoft Defender for Endpoint onboarded devices as a network data source to attribute activities to non-onboarded devices.</span></span> <span data-ttu-id="e66b9-160">Dies bedeutet, dass aktivitäten auf dem nicht integrierten Gerät auf der Zeitachse und in der Tabelle Advanced hunting DeviceNetworkEvents angezeigt werden, wenn ein integriertes Microsoft Defender for Endpoint-Gerät mit einem nicht integrierten Gerät kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="e66b9-160">This means that if a Microsoft Defender for Endpoint onboarded device communicated with a non-onboarded device, activities on the non-onboarded device can be seen on the timeline and through the Advanced hunting DeviceNetworkEvents table.</span></span> 



<span data-ttu-id="e66b9-161">Neue Ereignisse sind TCP(Transmission Control Protocol)-Verbindungen und passen zum aktuellen DeviceNetworkEvents-Schema.</span><span class="sxs-lookup"><span data-stu-id="e66b9-161">New events are Transmission Control Protocol (TCP) connections-based and will fit to the current DeviceNetworkEvents scheme.</span></span> <span data-ttu-id="e66b9-162">TCP-Ingress auf das Microsoft Defender for Endpoint-fähige Gerät von einem nicht von Microsoft Defender für Endpoint aktivierten Gerät.</span><span class="sxs-lookup"><span data-stu-id="e66b9-162">TCP ingress to the Microsoft Defender for Endpoint enabled device from a non-Microsoft Defender for Endpoint enabled.</span></span>  

<span data-ttu-id="e66b9-163">Außerdem wurden die folgenden Aktionstypen hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e66b9-163">The following action types have also been added:</span></span>  

- <span data-ttu-id="e66b9-164">ConnectionAttempt – Versuch, eine TCP-Verbindung herzustellen (syn)</span><span class="sxs-lookup"><span data-stu-id="e66b9-164">ConnectionAttempt - An attempt to establish a TCP connection (syn)</span></span>  
- <span data-ttu-id="e66b9-165">ConnectionAcknowledged – Eine Bestätigung, dass eine TCP-Verbindung akzeptiert wurde (syn\ack)</span><span class="sxs-lookup"><span data-stu-id="e66b9-165">ConnectionAcknowledged - An acknowledgment that a TCP connection was accepted (syn\ack)</span></span>  

<span data-ttu-id="e66b9-166">Sie können diese Beispielabfrage ausprobieren:</span><span class="sxs-lookup"><span data-stu-id="e66b9-166">You can try this example query:</span></span>  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a><span data-ttu-id="e66b9-167">Geändertes Verhalten</span><span class="sxs-lookup"><span data-stu-id="e66b9-167">Changed behavior</span></span>
<span data-ttu-id="e66b9-168">Im folgenden Abschnitt werden die Änderungen aufgeführt, die Sie in Microsoft Defender for Endpoint und/oder Microsoft 365 Security Center beobachten, wenn diese Funktion aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e66b9-168">The following section lists the changes you'll observe in Microsoft Defender for Endpoint and/or Microsoft 365 Security Center when this capability is enabled.</span></span> 
 
1.  <span data-ttu-id="e66b9-169">Geräte, die nicht in Microsoft Defender to Endpoint onboarded sind, werden voraussichtlich im Geräteinventar, in der erweiterten Suche und in API-Abfragen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-169">Devices that are not onboarded to Microsoft Defender to Endpoint are expected to appear in the device inventory, advanced hunting, and API queries.</span></span> <span data-ttu-id="e66b9-170">Dadurch kann die Größe der Abfrageergebnisse erheblich erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="e66b9-170">This may significantly increase the size of query results.</span></span> 
    1. <span data-ttu-id="e66b9-171">Die Tabellen "DeviceInfo" und "DeviceNetworkInfo" in Advanced Hunting enthalten nun ermitteltes Gerät.</span><span class="sxs-lookup"><span data-stu-id="e66b9-171">"DeviceInfo" and "DeviceNetworkInfo" tables in Advanced Hunting will now hold discovered device.</span></span> <span data-ttu-id="e66b9-172">Sie können diese Geräte mithilfe des Attributs "OnboardingStatus" herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-172">You can filter out those devices by using “OnboardingStatus” attribute.</span></span>

    2. <span data-ttu-id="e66b9-173">Ermittelte Geräte werden voraussichtlich in den Ergebnissen der Streaming-API-Abfrage angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e66b9-173">Discovered devices are expected to appear in Streaming API query results.</span></span> <span data-ttu-id="e66b9-174">Sie können diese Geräte mithilfe des Filters `OnboardingStatus` in Ihrer Abfrage herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="e66b9-174">You can filter out those devices by using the `OnboardingStatus` filter in your query.</span></span> 

2.  <span data-ttu-id="e66b9-175">Nicht verwaltete Geräte werden vorhandenen Gerätegruppen basierend auf den definierten Kriterien zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-175">Unmanaged devices will be assigned to existing device groups based on the defined criteria.</span></span> 
3.  <span data-ttu-id="e66b9-176">In seltenen Fällen kann die Standarderkennung Warnungen auf Netzwerkmonitoren oder Sicherheitstools auslösen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-176">In rare cases, Standard discovery might trigger alerts on network monitors or security tools.</span></span> <span data-ttu-id="e66b9-177">Bitte geben Sie Feedback, wenn solche Ereignisse auftreten, um zu verhindern, dass sich diese Probleme wiederholen.</span><span class="sxs-lookup"><span data-stu-id="e66b9-177">Please provide feedback, if you experience such events, to help prevent these issues from recurring.</span></span> <span data-ttu-id="e66b9-178">Sie können explizit ausschließen, dass bestimmte Ziele oder ganze Subnetze von der Standardermittlung aktiv untersucht werden.</span><span class="sxs-lookup"><span data-stu-id="e66b9-178">You can explicitly exclude specific targets or entire subnets from being actively probed by Standard discovery.</span></span> 



## <a name="next-steps"></a><span data-ttu-id="e66b9-179">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e66b9-179">Next steps</span></span>
- [<span data-ttu-id="e66b9-180">Konfigurieren der Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="e66b9-180">Configure device discovery</span></span>](configure-device-discovery.md)
- [<span data-ttu-id="e66b9-181">Häufig gestellte Fragen zur Geräteerkennung</span><span class="sxs-lookup"><span data-stu-id="e66b9-181">Device discovery FAQs</span></span>](device-discovery-faq.md)

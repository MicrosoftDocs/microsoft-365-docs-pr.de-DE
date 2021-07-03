---
title: Konfigurieren der Geräteermittlung
description: Erfahren Sie, wie Sie die Geräteermittlung in Microsoft 365 Defender mithilfe der Einfach- oder Standardermittlung konfigurieren.
keywords: einfach, Standard, Endpunktermittlung konfigurieren, Geräteermittlung
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
ms.openlocfilehash: ee56ed2949ea72771d8f08570d4352dbe7548d52
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286945"
---
# <a name="configure-device-discovery"></a><span data-ttu-id="8180a-104">Konfigurieren der Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="8180a-104">Configure device discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8180a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8180a-105">**Applies to:**</span></span>
- [<span data-ttu-id="8180a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8180a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8180a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8180a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="8180a-108">Die Ermittlung kann so konfiguriert werden, dass sie sich im Standard- oder Standardmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="8180a-108">Discovery can be configured to be on standard or basic mode.</span></span> <span data-ttu-id="8180a-109">Verwenden Sie die Standardoption, um Geräte in Ihrem Netzwerk aktiv zu finden, wodurch die Ermittlung von Endpunkten besser gewährleistet und eine umfassendere Geräteklassifizierung bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8180a-109">Use the standard option to actively find devices in your network, which will better guarantee the discovery of endpoints and provide richer device classification.</span></span> 

<span data-ttu-id="8180a-110">Sie können die Liste der Geräte anpassen, die für die Standardermittlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8180a-110">You can customize the list of devices that are used to perform standard discovery.</span></span> <span data-ttu-id="8180a-111">Sie können entweder die Standardermittlung auf allen integrierten Geräten aktivieren, die diese Funktion ebenfalls unterstützen (derzeit – nur Windows 10 Geräte) oder eine Teilmenge oder Teilmengen Ihrer Geräte auswählen, indem Sie deren Gerätetags angeben.</span><span class="sxs-lookup"><span data-stu-id="8180a-111">You can either enable standard discovery on all the onboarded devices that also support this capability (currently - Windows 10 devices only) or select a subset or subsets of your devices by specifying their device tags.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8180a-112">Für die Vorschau müssen Sie zuerst die Vorschaufeatures in Microsoft Defender Security Center aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8180a-112">For preview, you'll first need to turn on the Preview features in Microsoft Defender Security Center.</span></span>
> <span data-ttu-id="8180a-113">Anschließend können Sie auf die Geräteermittlungskonfiguration im Microsoft 365 Security Center zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8180a-113">You can then access the device discovery configuration in Microsoft 365 security center.</span></span> <span data-ttu-id="8180a-114">Die Liste der nicht verwalteten Geräte und Sicherheitsempfehlungen wird sowohl in Microsoft Defender Security Center als auch in Microsoft 365 Security Center verfügbar sein, während die Dashboardkacheln nur in Microsoft 365 Security Center verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="8180a-114">The list of unmanaged devices and security recommendations will be available in both Microsoft Defender Security Center and Microsoft 365 security center, while the dashboard tiles will only be available in Microsoft 365 security center.</span></span>

<span data-ttu-id="8180a-115">Führen Sie die folgenden Konfigurationsschritte im Microsoft 365 Security Center aus:</span><span class="sxs-lookup"><span data-stu-id="8180a-115">Take the following configuration steps in Microsoft 365 security center:</span></span>

1. <span data-ttu-id="8180a-116">Navigieren Sie zu **Einstellungen > Geräteermittlung.**</span><span class="sxs-lookup"><span data-stu-id="8180a-116">Navigate to **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="8180a-117">Wählen Sie den Ermittlungsmodus aus, der auf Ihren integrierten Geräten verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8180a-117">Select the discovery mode to use on your onboarded devices.</span></span>
3. <span data-ttu-id="8180a-118">Wenn Sie sich für die Verwendung der Standardermittlung entschieden haben, wählen Sie aus, welche Geräte für die aktive Untersuchung verwendet werden sollen: alle Geräte oder auf einer Teilmenge, indem Sie deren Gerätetags angeben.</span><span class="sxs-lookup"><span data-stu-id="8180a-118">If you've selected to use standard discovery, select which devices to use for active probing: all devices or on a subset by specifying their device tags.</span></span>
4. <span data-ttu-id="8180a-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="8180a-119">Click **Save**.</span></span>

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a><span data-ttu-id="8180a-120">Ausschließen, dass Geräte bei der Standardermittlung aktiv untersucht werden</span><span class="sxs-lookup"><span data-stu-id="8180a-120">Exclude devices from being actively probed in standard discovery</span></span>

<span data-ttu-id="8180a-121">Wenn in Ihrem Netzwerk Geräte vorhanden sind, die nicht aktiv gescannt werden sollten (z. B. Geräte, die alsPots für ein anderes Sicherheitstool verwendet werden), können Sie auch eine Liste von Ausschlüssen definieren, um zu verhindern, dass sie gescannt werden.</span><span class="sxs-lookup"><span data-stu-id="8180a-121">If there are devices on your network which should not be actively scanned (for example, devices used as honeypots for another security tool), you can also define a list of exclusions to prevent them from being scanned.</span></span> <span data-ttu-id="8180a-122">Beachten Sie, dass Geräte weiterhin im Basic-Ermittlungsmodus ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="8180a-122">Note that devices can still be discovered using Basic discovery mode.</span></span> <span data-ttu-id="8180a-123">Diese Geräte werden passiv erkannt, aber nicht aktiv untersucht.</span><span class="sxs-lookup"><span data-stu-id="8180a-123">Those devices will be passively discovered but won't be actively probed.</span></span> 

## <a name="select-networks-to-monitor"></a><span data-ttu-id="8180a-124">Auswählen von Netzwerken, die überwacht werden sollen</span><span class="sxs-lookup"><span data-stu-id="8180a-124">Select networks to monitor</span></span>

 <span data-ttu-id="8180a-125">Microsoft Defender für Endpunkt analysiert ein Netzwerk und ermittelt, ob es sich um ein Unternehmensnetzwerk handelt, das überwacht werden muss, oder um ein Nicht-Unternehmensnetzwerk, das ignoriert werden kann.</span><span class="sxs-lookup"><span data-stu-id="8180a-125">Microsoft Defender for Endpoint analyzes a network and determines if it is a corporate network that needs to be monitored or a non-corporate network that can be ignored.</span></span> <span data-ttu-id="8180a-126">Unternehmensnetzwerke werden in der Regel für die Überwachung ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8180a-126">Corporate networks are typically chosen to be monitored.</span></span> <span data-ttu-id="8180a-127">Sie können diese Entscheidung jedoch außer Kraft setzen, indem Sie auswählen, dass Nicht-Unternehmensnetzwerke überwacht werden, in denen integrierte Geräte gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="8180a-127">However, you can override this decision by choosing to monitor non-corporate networks where onboarded devices are found.</span></span> 

<span data-ttu-id="8180a-128">Sie können konfigurieren, wo die Geräteermittlung durchgeführt werden kann, indem Sie angeben, welche Netzwerke überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8180a-128">You can configure where device discovery can be performed by specifying which networks to monitor.</span></span> <span data-ttu-id="8180a-129">Wenn ein Netzwerk überwacht wird, kann die Geräteermittlung für es ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8180a-129">When a network is monitored, device discovery can be performed on it.</span></span> 

<span data-ttu-id="8180a-130">Eine Liste der Netzwerke, in denen die Geräteermittlung durchgeführt werden kann, wird auf der Seite **"Überwachte Netzwerke"** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8180a-130">A list of networks where device discovery can be performed is shown in the **Monitored networks** page.</span></span> 

> [!NOTE]
> <span data-ttu-id="8180a-131">Nur die 50 wichtigsten Netzwerke (entsprechend der Anzahl der zugeordneten Geräte) sind in der Netzwerkliste verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8180a-131">Only top 50 networks (according to the number of associated devices) will be available in the network list.</span></span> 

<span data-ttu-id="8180a-132">Die Liste der überwachten Netzwerke wird basierend auf der Gesamtzahl der Geräte sortiert, die in den letzten 7 Tagen im Netzwerk angezeigt wurden.</span><span class="sxs-lookup"><span data-stu-id="8180a-132">The list of monitored networks is sorted based upon the total number of devices seen on the network in the last 7 days.</span></span>

<span data-ttu-id="8180a-133">Sie können einen Filter anwenden, um einen der folgenden Netzwerkermittlungszustände anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8180a-133">You can apply a filter to view any of the following network discovery states:</span></span>

- <span data-ttu-id="8180a-134">**Überwachte Netzwerke** – Netzwerke, in denen die Geräteermittlung durchgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8180a-134">**Monitored networks** - Networks where device discovery is performed.</span></span>
- <span data-ttu-id="8180a-135">**Ignorierte Netzwerke–** Dieses Netzwerk wird ignoriert, und die Geräteermittlung wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="8180a-135">**Ignored networks** - This network will be ignored and device discovery will not be performed on it.</span></span>
- <span data-ttu-id="8180a-136">**Alle** – sowohl überwachte als auch ignorierte Netzwerke werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8180a-136">**All** - Both monitored and ignored networks will be displayed.</span></span>

### <a name="configure-the-network-monitor-state"></a><span data-ttu-id="8180a-137">Konfigurieren des Netzwerküberwachungsstatus</span><span class="sxs-lookup"><span data-stu-id="8180a-137">Configure the network monitor state</span></span>

<span data-ttu-id="8180a-138">Sie steuern, wo die Geräteermittlung stattfindet.</span><span class="sxs-lookup"><span data-stu-id="8180a-138">You control where device discovery takes place.</span></span> <span data-ttu-id="8180a-139">Überwachte Netzwerke sind der Ort, an dem die Geräteermittlung durchgeführt wird und in der Regel Unternehmensnetzwerke sind.</span><span class="sxs-lookup"><span data-stu-id="8180a-139">Monitored networks is where device discovery will be performed and are typically corporate networks.</span></span> <span data-ttu-id="8180a-140">Sie können auch auswählen, ob Netzwerke ignoriert oder die klassifizierung für die erste Ermittlung ausgewählt werden soll, nachdem Sie einen Status geändert haben.</span><span class="sxs-lookup"><span data-stu-id="8180a-140">You can also choose to ignore networks or select the initial discovery classification after modifying a state.</span></span>

<span data-ttu-id="8180a-141">Wenn Sie die anfängliche Ermittlungsklassifizierung auswählen, müssen Sie den standardmäßigen systembasierten Netzwerküberwachungsstatus anwenden.</span><span class="sxs-lookup"><span data-stu-id="8180a-141">Choosing the initial discovery classification means applying the default system-made network monitor state.</span></span> <span data-ttu-id="8180a-142">Das Auswählen des standardmäßigen systembasierten Netzwerküberwachungsstatus bedeutet, dass Netzwerke, die als Unternehmensnetzwerke identifiziert wurden, überwacht und als nicht unternehmenseigene Netzwerke identifiziert werden, automatisch ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="8180a-142">Selecting the default system-made network monitor state means that networks that were identified to be corporate, will be monitored, and ones identified as non-corporate, will be ignored automatically.</span></span>

1. <span data-ttu-id="8180a-143">Wählen Sie **Einstellungen > Geräteermittlung aus.**</span><span class="sxs-lookup"><span data-stu-id="8180a-143">Select **Settings > Device discovery**.</span></span>
2. <span data-ttu-id="8180a-144">Wählen Sie **überwachte Netzwerke** aus.</span><span class="sxs-lookup"><span data-stu-id="8180a-144">Select **Monitored networks**.</span></span>
3. <span data-ttu-id="8180a-145">Zeigen Sie die Liste der Netzwerke an.</span><span class="sxs-lookup"><span data-stu-id="8180a-145">View the list of networks.</span></span>
4. <span data-ttu-id="8180a-146">Wählen Sie die drei Punkte neben dem Netzwerknamen aus.</span><span class="sxs-lookup"><span data-stu-id="8180a-146">Select the three dots next to the network name.</span></span>
5. <span data-ttu-id="8180a-147">Wählen Sie aus, ob Sie die anfängliche Ermittlungsklassifizierung überwachen, ignorieren oder verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8180a-147">Choose whether you want to monitor, ignore, or use the initial discovery classification.</span></span>

    > [!WARNING]
    >
    > - <span data-ttu-id="8180a-148">Wenn Sie sich für die Überwachung eines Netzwerks entscheiden, das von Microsoft Defender für Endpunkt nicht als Unternehmensnetzwerk identifiziert wurde, kann dies zu einer Geräteermittlung außerhalb Ihres Unternehmensnetzwerks führen und kann daher private oder andere Nicht-Unternehmensgeräte erkennen.</span><span class="sxs-lookup"><span data-stu-id="8180a-148">Choosing to monitor a network that was not identified by Microsoft Defender for Endpoint as a corporate network can cause device discovery outside of your corporate network, and may therefore detect home or other non-corporate devices.</span></span>
    > - <span data-ttu-id="8180a-149">Wenn Sie ein Netzwerk ignorieren, wird die Überwachung und Ermittlung von Geräten in diesem Netzwerk beendet.</span><span class="sxs-lookup"><span data-stu-id="8180a-149">Choosing to ignore a network will stop monitoring and discovering devices in that network.</span></span> <span data-ttu-id="8180a-150">Geräte, die bereits ermittelt wurden, werden nicht aus dem Bestand entfernt, aber nicht mehr aktualisiert, und Details werden bis zum Ablauf des Datenaufbewahrungszeitraums von Defender für Endpunkt aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="8180a-150">Devices that were already discovered will not be removed from the inventory, but will no longer be updated, and details will be retained until the data retention period of the Defender for Endpoint expires.</span></span>
    > - <span data-ttu-id="8180a-151">Bevor Sie sich für die Überwachung von Nicht-Unternehmensnetzwerken entscheiden, müssen Sie sicherstellen, dass Sie dazu berechtigt sind.</span><span class="sxs-lookup"><span data-stu-id="8180a-151">Before choosing to monitor non-corporate networks, you must ensure you have permission to do so.</span></span>

6. <span data-ttu-id="8180a-152">Vergewissern Sie sich, dass Sie die Änderung vornehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="8180a-152">Confirm that you want to make the change.</span></span> 

## <a name="explore-devices-in-the-network"></a><span data-ttu-id="8180a-153">Erkunden von Geräten im Netzwerk</span><span class="sxs-lookup"><span data-stu-id="8180a-153">Explore devices in the network</span></span>

<span data-ttu-id="8180a-154">Sie können die folgende erweiterte Suchabfrage verwenden, um mehr Kontext zu jedem in der Netzwerkliste beschriebenen Netzwerknamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8180a-154">You can use the following advanced hunting query to get more context about each network name described in the networks list.</span></span> <span data-ttu-id="8180a-155">Die Abfrage listet alle integrierten Geräte auf, die innerhalb der letzten 7 Tage mit einem bestimmten Netzwerk verbunden waren.</span><span class="sxs-lookup"><span data-stu-id="8180a-155">The query lists all the onboarded devices that were connected to a certain network within the last 7 days.</span></span>

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| summarize arg_max(Timestamp, *) by DeviceId
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
```

## <a name="see-also"></a><span data-ttu-id="8180a-156">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8180a-156">See also</span></span>

- [<span data-ttu-id="8180a-157">Übersicht über die Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="8180a-157">Device discovery overview</span></span>](device-discovery.md)
- [<span data-ttu-id="8180a-158">Häufig gestellte Fragen zur Geräteermittlung</span><span class="sxs-lookup"><span data-stu-id="8180a-158">Device discovery FAQs</span></span>](device-discovery-faq.md)

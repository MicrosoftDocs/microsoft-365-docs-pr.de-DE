---
title: Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys
description: Erfahren Sie, wie Sie die erweiterte Überwachung auf HTTP-Ebene mithilfe von Netzwerkschutz in Microsoft Defender ATP verwenden, der anstelle eines Proxys ein echtes Ziel zeigt.
keywords: Proxy, Netzwerkschutz, Weiterleitungsproxy, Netzwerkereignisse, Überwachung, Block, Domänennamen, Domäne
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 28d8a113ed77e9624bd914571b1af4a7ece2aa5c
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587563"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a><span data-ttu-id="3d619-104">Untersuchen von Verbindungsereignissen hinter Weiterleitungsproxys</span><span class="sxs-lookup"><span data-stu-id="3d619-104">Investigate connection events that occur behind forward proxies</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="3d619-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3d619-105">**Applies to:**</span></span>
- [<span data-ttu-id="3d619-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3d619-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="3d619-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3d619-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="3d619-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="3d619-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="3d619-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="3d619-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

<span data-ttu-id="3d619-110">Defender for Endpoint unterstützt die Netzwerkverbindungsüberwachung von verschiedenen Ebenen des Netzwerkstapels.</span><span class="sxs-lookup"><span data-stu-id="3d619-110">Defender for Endpoint supports network connection monitoring from different levels of the network stack.</span></span> <span data-ttu-id="3d619-111">Ein anspruchsvoller Fall ist, wenn das Netzwerk einen Weiterleitungsproxy als Gateway zum Internet verwendet.</span><span class="sxs-lookup"><span data-stu-id="3d619-111">A challenging case is when the network uses a forward proxy as a gateway to the Internet.</span></span>

<span data-ttu-id="3d619-112">Der Proxy verhält sich so, als wäre er der Zielendpunkt.</span><span class="sxs-lookup"><span data-stu-id="3d619-112">The proxy acts as if it was the target endpoint.</span></span>  <span data-ttu-id="3d619-113">In diesen Fällen überwachen einfache Netzwerkverbindungsmonitore die Verbindungen mit dem Proxy, der korrekt ist, aber einen niedrigeren Untersuchungswert hat.</span><span class="sxs-lookup"><span data-stu-id="3d619-113">In these cases, simple network connection monitors will audit the connections with the proxy which is correct but has lower investigation value.</span></span> 

<span data-ttu-id="3d619-114">Defender for Endpoint unterstützt die erweiterte Überwachung auf HTTP-Ebene durch Netzwerkschutz.</span><span class="sxs-lookup"><span data-stu-id="3d619-114">Defender for Endpoint supports advanced HTTP level monitoring through network protection.</span></span> <span data-ttu-id="3d619-115">Wenn dies aktiviert ist, wird ein neuer Ereignistyp angezeigt, der die tatsächlichen Zieldomänennamen verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="3d619-115">When turned on, a new type of event is surfaced which exposes the real target domain names.</span></span>

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a><span data-ttu-id="3d619-116">Verwenden von Netzwerkschutz zum Überwachen der Netzwerkverbindung hinter einer Firewall</span><span class="sxs-lookup"><span data-stu-id="3d619-116">Use network protection to monitor network connection behind a firewall</span></span>
<span data-ttu-id="3d619-117">Die Überwachung der Netzwerkverbindung hinter einem Weiterleitungsproxy ist aufgrund zusätzlicher Netzwerkereignisse möglich, die aus dem Netzwerkschutz stammen.</span><span class="sxs-lookup"><span data-stu-id="3d619-117">Monitoring network connection behind a forward proxy is possible due to additional network events that originate from network protection.</span></span> <span data-ttu-id="3d619-118">Um sie auf einer Gerätezeitachse anzuzeigen, aktivieren Sie den Netzwerkschutz (mindestens im Überwachungsmodus).</span><span class="sxs-lookup"><span data-stu-id="3d619-118">To see them on a device timeline, turn network protection on (at the minimum in audit mode).</span></span> 

<span data-ttu-id="3d619-119">Der Netzwerkschutz kann mithilfe der folgenden Modi gesteuert werden:</span><span class="sxs-lookup"><span data-stu-id="3d619-119">Network protection can be controlled using the following modes:</span></span>

- <span data-ttu-id="3d619-120">**Blockieren**</span><span class="sxs-lookup"><span data-stu-id="3d619-120">**Block**</span></span> <br> <span data-ttu-id="3d619-121">Benutzer oder Apps werden an der Verbindung mit gefährlichen Domänen blockiert.</span><span class="sxs-lookup"><span data-stu-id="3d619-121">Users or apps will be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="3d619-122">Sie können diese Aktivität im Microsoft Defender Security Center sehen.</span><span class="sxs-lookup"><span data-stu-id="3d619-122">You will be able to see this activity in Microsoft Defender Security Center.</span></span>
- <span data-ttu-id="3d619-123">**Audit**</span><span class="sxs-lookup"><span data-stu-id="3d619-123">**Audit**</span></span> <br> <span data-ttu-id="3d619-124">Benutzer oder Apps werden nicht an der Verbindung mit gefährlichen Domänen blockiert.</span><span class="sxs-lookup"><span data-stu-id="3d619-124">Users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="3d619-125">Diese Aktivität wird jedoch weiterhin im Microsoft Defender Security Center zu sehen sein.</span><span class="sxs-lookup"><span data-stu-id="3d619-125">However, you will still see this activity in Microsoft Defender Security Center.</span></span>


<span data-ttu-id="3d619-126">Wenn Sie den Netzwerkschutz deaktivieren, werden Benutzer oder Apps nicht an der Verbindung mit gefährlichen Domänen blockiert.</span><span class="sxs-lookup"><span data-stu-id="3d619-126">If you turn network protection off, users or apps will not be blocked from connecting to dangerous domains.</span></span> <span data-ttu-id="3d619-127">Es werden keine Netzwerkaktivitäten im Microsoft Defender Security Center zu sehen sein.</span><span class="sxs-lookup"><span data-stu-id="3d619-127">You will not see any network activity in Microsoft Defender Security Center.</span></span>

<span data-ttu-id="3d619-128">Wenn Sie dies nicht konfigurieren, wird die Netzwerksperrung standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3d619-128">If you do not configure it, network blocking will be turned off by default.</span></span>

<span data-ttu-id="3d619-129">Weitere Informationen finden Sie unter [Aktivieren des Netzwerkschutzes](enable-network-protection.md).</span><span class="sxs-lookup"><span data-stu-id="3d619-129">For more information, see [Enable network protection](enable-network-protection.md).</span></span>

## <a name="investigation-impact"></a><span data-ttu-id="3d619-130">Untersuchungswirkung</span><span class="sxs-lookup"><span data-stu-id="3d619-130">Investigation impact</span></span>
<span data-ttu-id="3d619-131">Wenn der Netzwerkschutz aktiviert ist, wird auf der Zeitachse eines Geräts angezeigt, dass die IP-Adresse den Proxy weiterhin darstellt, während die tatsächliche Zieladresse angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3d619-131">When network protection is turned on, you'll see that on a device's timeline the IP address will keep representing the proxy, while the real target address shows up.</span></span>

![Abbildung von Netzwerkereignissen auf der Zeitachse des Geräts](images/atp-proxy-investigation.png)

<span data-ttu-id="3d619-133">Zusätzliche Ereignisse, die von der Netzwerkschutzebene ausgelöst werden, stehen nun zur Verfügung, um die tatsächlichen Domänennamen auch hinter einem Proxy zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3d619-133">Additional events triggered by the network protection layer are now available to surface the real domain names even behind a proxy.</span></span>

<span data-ttu-id="3d619-134">Informationen des Ereignisses:</span><span class="sxs-lookup"><span data-stu-id="3d619-134">Event's information:</span></span>

![Abbildung eines einzelnen Netzwerkereigniss](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a><span data-ttu-id="3d619-136">Suche nach Verbindungsereignissen mithilfe der erweiterten Suche</span><span class="sxs-lookup"><span data-stu-id="3d619-136">Hunt for connection events using advanced hunting</span></span> 
<span data-ttu-id="3d619-137">Alle neuen Verbindungsereignisse stehen Ihnen auch für die erweiterte Suche zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3d619-137">All new connection events are available for you to hunt on through advanced hunting as well.</span></span> <span data-ttu-id="3d619-138">Da es sich bei diesen Ereignissen um Verbindungsereignisse handelt, finden Sie sie unter der Tabelle DeviceNetworkEvents unter dem `ConnecionSuccess` Aktionstyp.</span><span class="sxs-lookup"><span data-stu-id="3d619-138">Since these events are connection events, you can find them under the DeviceNetworkEvents table under the `ConnecionSuccess` action type.</span></span>

<span data-ttu-id="3d619-139">Bei Verwendung dieser einfachen Abfrage werden alle relevanten Ereignisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3d619-139">Using this simple query will show you all the relevant events:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Abbildung der erweiterten Suchabfrage](images/atp-proxy-investigation-ah.png)

<span data-ttu-id="3d619-141">Sie können auch Ereignisse herausfiltern, die mit der Verbindung mit dem Proxy selbst verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="3d619-141">You can also filter out  events that are related to connection to the proxy itself.</span></span> 

<span data-ttu-id="3d619-142">Verwenden Sie die folgende Abfrage, um die Verbindungen mit dem Proxy herausfiltern:</span><span class="sxs-lookup"><span data-stu-id="3d619-142">Use the following query to filter out the connections to the proxy:</span></span>

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a><span data-ttu-id="3d619-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="3d619-143">Related topics</span></span>
- [<span data-ttu-id="3d619-144">Anwenden von Netzwerkschutz mit GP – Richtlinien-CSP</span><span class="sxs-lookup"><span data-stu-id="3d619-144">Applying network protection with GP - policy CSP</span></span>](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)

---
title: Microsoft 365 Network Insights (Vorschau)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Network Insights (Vorschau)
ms.openlocfilehash: b30af89d480383fdc9011d24409e3b418339c70b
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690569"
---
# <a name="microsoft-365-network-insights-preview"></a><span data-ttu-id="7be50-103">Microsoft 365 Network Insights (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7be50-103">Microsoft 365 Network Insights (preview)</span></span>

<span data-ttu-id="7be50-104">**Network Insights** sind Live-Leistungs Metriken, die von Ihrem Microsoft 365-Mandanten gesammelt werden und nur für administrative Benutzer in Ihrem Mandanten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7be50-104">**Network insights** are live performance metrics collected from your Microsoft 365 tenant, and available to view only by administrative users in your tenant.</span></span> <span data-ttu-id="7be50-105">Einblicke werden im Microsoft 365 Admin Center unter angezeigt <https://portal.microsoft.com/adminportal/home#/networkperformance> .</span><span class="sxs-lookup"><span data-stu-id="7be50-105">Insights are displayed in the Microsoft 365 Admin Center at <https://portal.microsoft.com/adminportal/home#/networkperformance>.</span></span>

<span data-ttu-id="7be50-106">Mithilfe von Insights sollen Netzwerkperimeter für Ihre Office-Standorte entworfen werden.</span><span class="sxs-lookup"><span data-stu-id="7be50-106">Insights are intended to help in designing network perimeters for your office locations.</span></span> <span data-ttu-id="7be50-107">Jede Insight enthält Live-Details zu den Leistungsmerkmalen eines bestimmten allgemeinen Problems für jeden geografischen Standort, auf den Benutzer auf ihren Mandanten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7be50-107">Each insight provides live details about the performance characteristics for a specific common issue for each geographic location where users are accessing your tenant.</span></span>

<span data-ttu-id="7be50-108">Es gibt fünf spezifische Netzwerk Einblicke, die für jeden Office-Standort angezeigt werden können:</span><span class="sxs-lookup"><span data-stu-id="7be50-108">There are five specific network insights that may be shown for each office location:</span></span>

- [<span data-ttu-id="7be50-109">Ausstieg aus dem backhauld-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="7be50-109">Backhauled network egress</span></span>](#backhauled-network-egress)
- [<span data-ttu-id="7be50-110">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="7be50-110">Better performance detected for customers near you</span></span>](#better-performance-detected-for-customers-near-you)
- [<span data-ttu-id="7be50-111">Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="7be50-111">Use of a non-optimal Exchange Online service front door</span></span>](#use-of-a-non-optimal-exchange-online-service-front-door)
- [<span data-ttu-id="7be50-112">Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="7be50-112">Use of a non-optimal SharePoint Online service front door</span></span>](#use-of-a-non-optimal-sharepoint-online-service-front-door)
- [<span data-ttu-id="7be50-113">Niedrige Downloadgeschwindigkeit von SharePoint-Haustür</span><span class="sxs-lookup"><span data-stu-id="7be50-113">Low download speed from SharePoint front door</span></span>](#low-download-speed-from-sharepoint-front-door)

>[!IMPORTANT]
><span data-ttu-id="7be50-114">Netzwerk Einblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und stehen nur für Microsoft 365-Mandanten zur Verfügung, die im Feature Preview-Programm registriert wurden.</span><span class="sxs-lookup"><span data-stu-id="7be50-114">Network insights, performance recommendations and assessments in the Microsoft 365 Admin Center is currently in preview status, and is only available for Microsoft 365 tenants that have been enrolled in the feature preview program.</span></span>

## <a name="backhauled-network-egress"></a><span data-ttu-id="7be50-115">Ausstieg aus dem backhauld-Netzwerk</span><span class="sxs-lookup"><span data-stu-id="7be50-115">Backhauled network egress</span></span>

<span data-ttu-id="7be50-116">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass der Abstand zwischen einem bestimmten Benutzerstandort und dem Netzwerk Ausgang größer als 500 Meilen (800 Kilometer) ist und angibt, dass der Microsoft 365-Datenverkehr zu einem gemeinsamen Internet-Edge-Gerät oder-Proxy zurückgezogen wird.</span><span class="sxs-lookup"><span data-stu-id="7be50-116">This insight will be displayed if the network insights service detects that the distance from a given user location to the network egress is greater than 500 miles (800 kilometers), indicating that Microsoft 365 traffic is being backhauled to a common Internet edge device or proxy.</span></span>

<span data-ttu-id="7be50-117">Diese Einblicke wird in einigen zusammenfassungsansichten als "Ausstieg" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="7be50-117">This insight is abbreviated as "Egress" in some summary views.</span></span>

![Ausstieg aus dem backhauld-Netzwerk](../media/m365-mac-perf/m365-mac-perf-insights-detail-backhauled.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-119">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-119">What does this mean?</span></span>

<span data-ttu-id="7be50-120">Dadurch wird feststellen, dass der Abstand zwischen dem Bürostandort und dem Netzwerk Ausstieg mehr als 500 Meilen (800 Kilometer) beträgt.</span><span class="sxs-lookup"><span data-stu-id="7be50-120">This identifies that the distance between the office location and the network egress is more than 500 miles (800 kilometers).</span></span> <span data-ttu-id="7be50-121">Der Standort des Büros wird durch einen verborgenen Clientcomputer Speicherort identifiziert, und der Netzwerk Ausgangsspeicherort wird mithilfe von Reverse IP Address to Location Databases identifiziert.</span><span class="sxs-lookup"><span data-stu-id="7be50-121">The office location is identified by an obfuscated client machine location and the network egress location is identified by using reverse IP Address to location databases.</span></span> <span data-ttu-id="7be50-122">Der Office-Standort ist möglicherweise ungenau, wenn Windows-Ortungsdienste auf Computern deaktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="7be50-122">The office location may be inaccurate if Windows Location Services is disabled on machines.</span></span> <span data-ttu-id="7be50-123">Der Netzwerk Ausgangsspeicherort ist möglicherweise ungenau, wenn die Datenbankinformationen der Reverse-IP-Adresse ungenau sind.</span><span class="sxs-lookup"><span data-stu-id="7be50-123">The network egress location may be inaccurate if the reverse IP Address database information is inaccurate.</span></span>

<span data-ttu-id="7be50-124">Details für diese Einblicke sind der Office-Standort, der geschätzte Prozentsatz des Gesamt Mandanten Benutzers am Standort, der aktuelle Netzwerk Ausgangsstandort, die Relevanz des Ausgangs Standorts, der Abstand zwischen dem Standort und dem aktuellen Ausgangspunkt, das Datum, an dem die Bedingung erstmals erkannt wurde, und das Datum, an dem die Bedingung aufgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="7be50-124">Details for this insight include the office location, estimated percentage of total tenant user at the location, the current network egress location, relevance of the egress location, the distance between the location and the current egress point, the date the condition was first detected, and the date the condition was resolved.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-125">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-125">What should I do?</span></span>

<span data-ttu-id="7be50-126">Für diese Einblicke empfehlen wir den Netzwerk Ausstieg näher am Office-Standort, damit die Konnektivität optimal zum globalen Microsoft-Netzwerk und zur nächsten Microsoft 365-Dienst Haustür weitergeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="7be50-126">For this insight, we would recommend network egress closer to the office location so that connectivity can route optimally to Microsoft's global network and to the nearest Microsoft 365 service front door.</span></span> <span data-ttu-id="7be50-127">Das Schließen des Netzwerk Ausstiegs für Benutzer in Office-Standorten ermöglicht auch in Zukunft eine verbesserte Leistung, da Microsoft in Zukunft sowohl Netzwerk Points of Presence als auch Microsoft 365 Service-Front-Doors erweitert.</span><span class="sxs-lookup"><span data-stu-id="7be50-127">Having close network egress to users office locations also allows for improved performance in the future as Microsoft expands both network points of presence and Microsoft 365 service front doors in the future.</span></span>

<span data-ttu-id="7be50-128">Weitere Informationen zum Beheben dieses Problems finden Sie unter Ausgangs [Netzwerkverbindungen lokal](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Netzwerk Verbindungs Prinzipien](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="7be50-128">For more information about how to resolve this issue, see [Egress network connections locally](microsoft-365-network-connectivity-principles.md#egress-network-connections-locally) in [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="better-performance-detected-for-customers-near-you"></a><span data-ttu-id="7be50-129">Bessere Leistung für Kunden in Ihrer Nähe erkannt</span><span class="sxs-lookup"><span data-stu-id="7be50-129">Better performance detected for customers near you</span></span>

<span data-ttu-id="7be50-130">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass eine beträchtliche Anzahl von Kunden in Ihrem Metro-Bereich eine bessere Leistung hat als Benutzer in Ihrer Organisation an diesem Standort.</span><span class="sxs-lookup"><span data-stu-id="7be50-130">This insight will be displayed if the network insights service detects that a significant number of customers in your metro area have better performance than users in your organization at this office location.</span></span>

<span data-ttu-id="7be50-131">Diese Einblicke wird in einigen zusammenfassungsansichten als "Peers" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="7be50-131">This insight is abbreviated as "Peers" in some summary views.</span></span>

![Relative Netzwerkleistung](../media/m365-mac-perf/m365-mac-perf-insights-detail-cust-near-you.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-133">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-133">What does this mean?</span></span>

<span data-ttu-id="7be50-134">In dieser Einblicke wird die Gesamtleistung von Microsoft 365-Kunden in derselben Stadt wie dieser Standort untersucht.</span><span class="sxs-lookup"><span data-stu-id="7be50-134">This insight examines the aggregate performance of Microsoft 365 customers in the same city as this office location.</span></span> <span data-ttu-id="7be50-135">Diese Einblicke wird angezeigt, wenn die durchschnittliche Wartezeit Ihrer Benutzer 10% über der durchschnittlichen Wartezeit von benachbarten Mandanten liegt.</span><span class="sxs-lookup"><span data-stu-id="7be50-135">This insight is displayed if the average latency of your users is 10% greater than the average latency of neighboring tenants.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-136">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-136">What should I do?</span></span>

<span data-ttu-id="7be50-137">Es kann viele Gründe für diese Bedingung geben, einschließlich Wartezeit in Ihrem Unternehmensnetzwerk oder ISP, Engpässe oder Architektur Designprobleme.</span><span class="sxs-lookup"><span data-stu-id="7be50-137">There could be many reasons for this condition, including latency in your corporate network or ISP, bottlenecks, or architecture design issues.</span></span> <span data-ttu-id="7be50-138">Überprüfen Sie die Wartezeit zwischen den einzelnen Hops in der Route zwischen Ihrem Office-Netzwerk und der aktuellen Microsoft 365-Haustür.</span><span class="sxs-lookup"><span data-stu-id="7be50-138">Examine the latency between each hop in the route between your office network and the current Microsoft 365 front door.</span></span> <span data-ttu-id="7be50-139">Weitere Informationen finden Sie unter [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span><span class="sxs-lookup"><span data-stu-id="7be50-139">For more information, see [Office 365 Network Connectivity Principles](microsoft-365-network-connectivity-principles.md).</span></span>

## <a name="use-of-a-non-optimal-exchange-online-service-front-door"></a><span data-ttu-id="7be50-140">Verwenden eines nicht optimalen Exchange Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="7be50-140">Use of a non-optimal Exchange Online service front door</span></span>

<span data-ttu-id="7be50-141">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit einer optimalen Exchange Online Dienst-Haustür herstellen.</span><span class="sxs-lookup"><span data-stu-id="7be50-141">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to an optimal Exchange Online service front door.</span></span>

<span data-ttu-id="7be50-142">Diese Einblicke wird in einigen zusammenfassungsansichten als "Routing" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="7be50-142">This insight is abbreviated as "Routing" in some summary views.</span></span>

![Nicht optimale Eingangstür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-exo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-144">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-144">What does this mean?</span></span>

<span data-ttu-id="7be50-145">Wir führen Exchange Online Service-Fronttüren auf, die für die Verwendung aus der Office-Standort Stadt mit guter Leistung geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="7be50-145">We list Exchange Online service front doors which are suitable for use from the office location city with good performance.</span></span> <span data-ttu-id="7be50-146">Wenn der aktuelle Test die Verwendung eines Exchange Online-Dienst-Front-Doors nicht in dieser Liste zeigt, wird diese Empfehlung aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7be50-146">If the current test shows use of an Exchange Online service front door not on this list, then we call out this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-147">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-147">What should I do?</span></span>

<span data-ttu-id="7be50-148">Die Verwendung eines nicht optimalen Exchange Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="7be50-148">Use of a non-optimal Exchange Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="7be50-149">Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.</span><span class="sxs-lookup"><span data-stu-id="7be50-149">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="use-of-a-non-optimal-sharepoint-online-service-front-door"></a><span data-ttu-id="7be50-150">Verwenden eines nicht optimalen SharePoint Online-Dienst-Front-Door</span><span class="sxs-lookup"><span data-stu-id="7be50-150">Use of a non-optimal SharePoint Online service front door</span></span>

<span data-ttu-id="7be50-151">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass Benutzer an einem bestimmten Standort keine Verbindung mit der nächstgelegenen SharePoint Online Dienst-Haustür herstellen.</span><span class="sxs-lookup"><span data-stu-id="7be50-151">This insight will be displayed if the network insights service detects that users in a specific location are not connecting to the closest SharePoint Online service front door.</span></span>

<span data-ttu-id="7be50-152">Diese Einblicke wird in einigen zusammenfassungsansichten als "ausschließend" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="7be50-152">This insight is abbreviated as "Afd" in some summary views.</span></span>

![Nicht optimale Eingangstür](../media/m365-mac-perf/m365-mac-perf-insights-detail-front-door-spo.png)

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-154">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-154">What does this mean?</span></span>

<span data-ttu-id="7be50-155">Wir identifizieren die SharePoint Online-Dienst-Haustür, mit der der Testclient eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="7be50-155">We identify the SharePoint Online service front door that the test client is connecting to.</span></span> <span data-ttu-id="7be50-156">Für die Office-Standort Stadt vergleichen wir dies mit der erwarteten SharePoint Online-Service-Haustür für diese Stadt.</span><span class="sxs-lookup"><span data-stu-id="7be50-156">Then for the office location city we compare that to the expected SharePoint Online service front door for that city.</span></span> <span data-ttu-id="7be50-157">Wenn er nicht übereinstimmt, machen wir diese Empfehlung.</span><span class="sxs-lookup"><span data-stu-id="7be50-157">If it doesn't match, then we make this recommendation.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-158">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-158">What should I do?</span></span>

<span data-ttu-id="7be50-159">Die Verwendung eines nicht optimalen SharePoint Online Dienst-Front-Door könnte durch Netzwerk Backhaul vor dem Ausstieg des Unternehmensnetzwerks verursacht werden, in diesem Fall empfehlen wir den Ausstieg aus dem lokalen und direkten Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="7be50-159">Use of a non-optimal SharePoint Online service front door could be caused by network backhaul before the corporate network egress in which case we recommend local and direct network egress.</span></span> <span data-ttu-id="7be50-160">Es kann auch durch die Verwendung eines Remote-DNS-rekursive Auflösungs Servers verursacht werden, in dem der Fall empfohlen wird, den DNS-rekursive Auflösungs Server mit dem Netzwerk Ausstieg auszurichten.</span><span class="sxs-lookup"><span data-stu-id="7be50-160">It could also be caused by use of a remote DNS Recursive Resolver server in which case we recommend aligning the DNS Recursive Resolver server with the network egress.</span></span>

## <a name="low-download-speed-from-sharepoint-front-door"></a><span data-ttu-id="7be50-161">Niedrige Downloadgeschwindigkeit von SharePoint-Haustür</span><span class="sxs-lookup"><span data-stu-id="7be50-161">Low download speed from SharePoint front door</span></span>

<span data-ttu-id="7be50-162">Diese Einblicke werden angezeigt, wenn der Network Insights-Dienst erkennt, dass die Bandbreite zwischen dem jeweiligen Office-Standort und SharePoint Online kleiner als 1 Mbit/s ist.</span><span class="sxs-lookup"><span data-stu-id="7be50-162">This insight will be displayed if the network insights service detects that bandwidth between the specific office location and SharePoint Online is less than 1 MBps.</span></span>

<span data-ttu-id="7be50-163">Diese Einblicke wird in einigen zusammenfassungsansichten als "Durchsatz" abgekürzt.</span><span class="sxs-lookup"><span data-stu-id="7be50-163">This insight is abbreviated as "Throughput" in some summary views.</span></span>

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-164">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-164">What does this mean?</span></span>

<span data-ttu-id="7be50-165">Die Downloadgeschwindigkeit, die ein Benutzer von SharePoint Online-und OneDrive für Unternehmen-Dienst-Fronttüren erhalten kann, wird in Megabytes pro Sekunde (Mbps) gemessen.</span><span class="sxs-lookup"><span data-stu-id="7be50-165">The download speed that a user can get from SharePoint Online and OneDrive for Business service front doors is measured in megabytes per second (MBps).</span></span> <span data-ttu-id="7be50-166">Wenn dieser Wert kleiner als 1 Mbit/s ist, stellen wir diese Einblicke bereit.</span><span class="sxs-lookup"><span data-stu-id="7be50-166">If this value is less than 1 MBps then we provide this insight.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-167">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-167">What should I do?</span></span>

<span data-ttu-id="7be50-168">Um die Downloadgeschwindigkeit zu verbessern, muss die Bandbreite möglicherweise erhöht werden.</span><span class="sxs-lookup"><span data-stu-id="7be50-168">To improve download speeds, bandwidth may need to be increased.</span></span> <span data-ttu-id="7be50-169">Alternativ kann es zu Netzwerküberlastung zwischen Benutzercomputern am Office-Standort und der Front-Door-SharePoint Online Dienst geben.</span><span class="sxs-lookup"><span data-stu-id="7be50-169">Alternatively, there may be network congestion between user machines at the office location and the SharePoint Online service front door.</span></span> <span data-ttu-id="7be50-170">Dies wird manchmal als Überlastungs Verlust bezeichnet und schränkt die Downloadgeschwindigkeit ein, die Benutzern zur Verfügung steht, auch wenn genügend Bandbreite zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7be50-170">This is sometimes called congestive loss and it restricts the download speed available to users even if sufficient bandwidth is available.</span></span>

## <a name="china-user-optimal-network-egress"></a><span data-ttu-id="7be50-171">China-Benutzer optimales Netzwerk Austritt</span><span class="sxs-lookup"><span data-stu-id="7be50-171">China user optimal network egress</span></span>

<span data-ttu-id="7be50-172">Diese Einblicke werden angezeigt, wenn Ihre Organisation über Benutzer in China verfügt, die sich mit Ihrem Microsoft 365-Mandanten an anderen geografischen Standorten verbinden.</span><span class="sxs-lookup"><span data-stu-id="7be50-172">This insight will be displayed if your organization has users in China connecting to your Microsoft 365 tenant in other geographic locations.</span></span> 

### <a name="what-does-this-mean"></a><span data-ttu-id="7be50-173">Szenario</span><span class="sxs-lookup"><span data-stu-id="7be50-173">What does this mean?</span></span>

<span data-ttu-id="7be50-174">Wenn Ihre Organisation über private WAN-Konnektivität verfügt, wird empfohlen, eine Netzwerk-WAN-Schaltung von Ihren Office-Standorten in China aus zu konfigurieren, die über einen Netzwerk Austritt mit dem Internet an einem der folgenden Standorte verfügt:</span><span class="sxs-lookup"><span data-stu-id="7be50-174">If your organization has private WAN connectivity, we recommend configuring a network WAN circuit from your office locations in China that has network egress to the Internet in any of the following locations:</span></span>

- <span data-ttu-id="7be50-175">Hongkong (SAR)</span><span class="sxs-lookup"><span data-stu-id="7be50-175">Hong Kong</span></span>
- <span data-ttu-id="7be50-176">Japan</span><span class="sxs-lookup"><span data-stu-id="7be50-176">Japan</span></span>
- <span data-ttu-id="7be50-177">Taiwan</span><span class="sxs-lookup"><span data-stu-id="7be50-177">Taiwan</span></span>
- <span data-ttu-id="7be50-178">Südkorea</span><span class="sxs-lookup"><span data-stu-id="7be50-178">South Korea</span></span>
- <span data-ttu-id="7be50-179">Singapur</span><span class="sxs-lookup"><span data-stu-id="7be50-179">Singapore</span></span>
- <span data-ttu-id="7be50-180">Malaysia</span><span class="sxs-lookup"><span data-stu-id="7be50-180">Malaysia</span></span>

<span data-ttu-id="7be50-181">Internet Ausstieg weiter Weg von Benutzern als diese Standorte verringern die Leistung, und der Ausstieg in China kann aufgrund von grenzüberschreitender Überlastung zu hohen Latenz-und Verbindungsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="7be50-181">Internet egress further away from users than these locations will reduce performance, and egress in China may cause high latency and connectivity issues due to cross-border congestion.</span></span>

### <a name="what-should-i-do"></a><span data-ttu-id="7be50-182">Was soll ich machen?</span><span class="sxs-lookup"><span data-stu-id="7be50-182">What should I do?</span></span>

<span data-ttu-id="7be50-183">Weitere Informationen zum Minimieren von Leistungsproblemen im Zusammenhang mit dieser Einblicke finden Sie unter [Office 365 Global Tenant Performance Optimization for China users](microsoft-365-networking-china.md).</span><span class="sxs-lookup"><span data-stu-id="7be50-183">For more information about how to mitigate performance issues related to this insight, see [Office 365 global tenant performance optimization for China users](microsoft-365-networking-china.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7be50-184">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="7be50-184">Related topics</span></span>

[<span data-ttu-id="7be50-185">Empfehlungen zur Netzwerkleistung im Microsoft 365 Admin Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7be50-185">Network performance recommendations in the Microsoft 365 Admin Center (preview)</span></span>](office-365-network-mac-perf-overview.md)

[<span data-ttu-id="7be50-186">Microsoft 365 Netzwerkbewertung (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7be50-186">Microsoft 365 network assessment (preview)</span></span>](office-365-network-mac-perf-score.md)

[<span data-ttu-id="7be50-187">Microsoft 365 Connectivity Test im M365 Admin Center (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7be50-187">Microsoft 365 connectivity test in the M365 Admin Center (preview)</span></span>](office-365-network-mac-perf-onboarding-tool.md)

[<span data-ttu-id="7be50-188">Microsoft 365 Network Connectivity Location Services (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="7be50-188">Microsoft 365 Network Connectivity Location Services (preview)</span></span>](office-365-network-mac-location-services.md)